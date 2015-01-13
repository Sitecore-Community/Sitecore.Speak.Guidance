# Code Guidelines for JavaScript (Core 1.1 only)

The following guidelines apply to JavaScript for components that work for the 1.1 version of the SPEAK Core.

## General Guidelines 

- Follow the All Language Styling guidelines.

- Follow the standard JavaScript guidelines except when they conflict with the guidelines below.

## Component-Specific Guidelines 

- Configure the component to inherit from the proper base component.

- Always use `get`and `set` methods, as direct assignment will break binding.

  + Download the [SPEAK Events module](https://gist.github.com/dervalp/144ca3f5489b0d0d827a)

  + Require it, and extend it:


`

    define(["/path/to/speakevent.js", "underscore"], function (events, _)  {  

     var API = {}  

      _.extend(API, events);  

      return API;  

    });  

- Use the following code to trigger an event: `API.trigger("events");`

  + The implementations is a modified version of Backbone.js. [Read more about the API here](http://backbonejs.org/#Events)


