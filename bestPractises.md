#Best Practises

##General

##Follow the component check list document.

Each time you create a new component, make sure you follow all the steps mentioned in the [component check list](componentCheckList.md).

By following this list, you will be sure that your component is located on the right place and has the right style. This is already a good thing for maintenance.

##Javascript

###Avoid exposing in the global Object

If there would be only one, that would be it.

Avoid at any cost using the window object. SPEAK comes with a famous library called RequireJS. RequireJS helps you writing small modules and express the depedencies between them.

Before using SPEAK, I think you should at least know the basic of RequireJS. So, please, read [this](http://requirejs.org/docs/start.html), 5 minutes which will prevent you huge mistakes.

**What do I do if I have data exposed on the global object**

Too often I see code like this:

```
   window.MySubLibrary = window.MySubLibrary || {};

   window.MySubLibrary.doSomething = function () {};
```

Why is it bad?

First, you are making your MySubLibrary available by everyone. This means  any code written and exposed in that sort would be hard to track.

Second, you giving the possiblity to anyone to override your implementation.

Anyone could do:

```
   window.MySubLibrary = "bad code";

```

I will stop there and if you want more information, you can read "[why global variables are bad](http://c2.com/cgi/wiki?GlobalVariablesAreBad)" and this [stackoverflow thread](http://stackoverflow.com/questions/2613310/ive-heard-global-variables-are-bad-what-alternative-solution-should-i-use)

To correct this, it is easy: you need to define a Module using require:

```
define(["jquery"], function (jQuery) {
  var API = {
    doSomething: function () {
        alert("hello world!");
    }
  };

  return API;
});
```

By using require to create the module, your API won't be exposed in the global object. You will need to "require" it to get access.

```
    define(["/path/to/module/api.js"], function (myApi){
        console.log(myApi); //you have now access to your API.
    });
```

As you can see, it will make your code more maintanable as you will need to express your dependencies for each module. Moreover, Require comes with a shim to manage the ordering of your dependencies. You will now be "in control". Easier to maintain, easier to test.

###Always use "get" and "set" in SPEAK 1.1.

In 1.1, The good way to get a value is:

```
  myComponent.get("MyProperty");
```

And to set a value:

```
  myComponent.set("MyProperty", "some random value");
```

**DO NOT DO:**

```
  myComponent.attributes.MyProperty = "some random value";
```
This will BREAK the SPEAK Bindings !

###Use regular assignation in 1.2 but GET/SET is ok.

In 1.2, use:

```
  //set a value
  myComponent.MyProperty = "some value";
  //get a value
  alert(myComponent.MyProperty);
```

GET and SET will still work but regular assignation makes the code more readable.

###Separate DOM works from regular Javascript.

DOM is slow, javascript is fast. When you write a module always ensure to do your DOM work only once.

Example:

DO NOT DO:

```
  setInterval(function(){
    $("#someDiv").html("test");
  }, 500);
```

DO:

```
  var $someDiv = $("#someDiv");
  setInterval(function(){
    $someDiv.html("test");
  }, 500);
```

###Use $ prefix for jQuery object.

DO NOT:

```
    var someDiv = $("#someDiv");
```

DO:

```
    var $someDiv = $("#someDiv");
```

It will avoid you doing things like:

```
    var someDiv = $("#someDiv");
    //some code
    $(someDiv).html("that's bad!");
```

###Create helpers for the DOM

In the same way you want to separate your DOM works on a file, you maybe want to explicitly having a module handling all your dom Object.

Ex:

```
define(["jquery"], function (jQuery) {

  var $notificationBar = $("#notificationBar"),
      $mainMenu = $("#mainMenu"),
      $header = $("#header")

  var DOMHelper = {
    showNotification: function () {
        $notificationBar.show();
    },
    hideMenu: function () {
        $mainMenu.hide();
    },
    insertCodeInHeader: function (value) {
        $header.html("<span clas='someClass'>some " + value + " to insert</span>"); //this should be avoided
    }
  };

  return DOMHelper;
});
```

By having all your DOM manipulation in separate modules, you can quickly find what kind of HTML is needed for your page to work. Moreover, if you are inserting HTML in the page (something you should not do), you can quickly all the CSS classes or IDs.

###Separation of Concern, do use event.

It is important that your component you should not rely on any other custom code you have created for you application.

If you have something like:

```
  someComponentMethod: function () {
    Sitecore.MySubLibrary.doSomething();
  }
```

This is "really bad" as your are coupling Sitecore.MySubLibrary with your component. 

If you need to communicate from your component with the external world, use your Property or your Events.

**When to use Property ?**

You use property when you are able to use DataBinding to express your change. If you set some items to a components, this will let you do databinding between that component and another one using ROCKS.

You also use property when it makes sense for your component to have that property express in the Component Parameters.

**How to use Property ?**

Triggering the change by setting the value:

For 1.1:

```
  someComponentMethod: function () {
    this.model.set("items", [{ test: "some value" }]);
  }
```

For 1.2
```
  someComponentMethod: function () {
    this.items = [{ test: "some value" }];
  }
```

Listen for a change event ?

If you are not able to use databinding or need to do more complex work, you listen for the change in your pageCode.

In your pageCode:

```
  this.myComponent.on("change:items", someCallback);
```

**When to use Event ?**

When you can't use property.

**How to use Event?**

Triggering an event in the Component:

For 1.1:

```
  someComponentMethod: function () {
    this.model.trigger("somethingimportant", { test: "somevalue "});
  }
```

For 1.2:

```
  someComponentMethod: function () {
    this.trigger("somethingimportant", { test: "somevalue "});
  }
```

Listen for an event:

In your page code:

```
   this.myComponent.on("somethingimportant", doSomeCallback);
```

###NEVER EVER REFERENCE A COMPONENT OUTSIDE A PAGE CODE OR ANOTHER COMPONENT!

This is important !!!!!! You should never pass a component to a method which is not part of another component or the pageCode itself.

How do I communicate between some custom modules and my components?

**By using the pageCode and an event emitter in your custom module.**

In your pageCode you would do:

```
   myCustomModule.on("someGenericEvent", function (someValue) {
    this.MyComponent.set("someProperty", someValue);
   }, this);
```

**Your pagecode is the glue between your components and your modules!!!**

**If you do not have a pageCode for a complex page, sorry but you are doing all wrong**

**Just to be sure you get it, NEVER REFERENCE A COMPONENT OUTSIDE A PAGE CODE OR ANOTHER COMPONENT !!!**

I think now you get it but just to be clear, if one day I see someone doing that, I will virtually slap her/him, got it? :)

How to use an Event Emitter:

In 1.2, you can do:

```
define(["sitecore"], function (_sc) {

  var API = {}

  _sc.extend(API, _sc.utils.Events);

  return API;
});
```

In 1.1, you can do:

Download the SPEAK Events: https://gist.github.com/dervalp/144ca3f5489b0d0d827a

Require it, and extend it:

```
define(["/path/to/speakevent.js", "underscore"], function (events, _) {

  var API = {}

  _.extend(API, events);

  return API;
});
```

How to use?

```
   API.trigger("events");
```

The implementations is a modified version of the Backbone.js one. You can find documentation of the API here: http://backbonejs.org/#Events


##.NET

To be continued.