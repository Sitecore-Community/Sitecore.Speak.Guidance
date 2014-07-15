#SPEAK Component Guidelines

A SPEAK component is generally composed by a Razor File (.cshtml), a JavaScript file and a bunch of CSS.

##Components Structure.

When you create components for your Business Application or an entire component library, you should always use the same structure as the BCL structure.

Do not forget, if you create a business application, this structure needs to be placed under the **Common** folder.

**Please follow to the [component structure guideline](componentStructure.md) for more information** 

##Naming

A component name is **PascalCase**.

All the files related to a component **must** have the same name and same case.

- NameOfComponent.cshtml
- NameOfComponent.js
- NameOfComponent.(less|css)

All Items related to the component containing the Name should also be PascalCase.

If the component is brand new and has not relation with an existing one, please try to give it a meaningful name.

If the component is an extension of an existing component in the BCL, you should name **[app_name]NameOfTheComponent**


### !important! Never use a component from another Sitecore Business Application.


##Coding Style

BCL is based on bootstrap. Therefore, we have adopted their code style guide for HTML and CSS.

####Razor

**Never put HTML in C#, HTML must be in cshtml file and not inside C#**. Having HTML in C# makes the maintenance and the styling of your component a nightmare for everyone.

*NOTE: As you can see, we did that mistake in previous version of SPEAK. When we needed to upgrade the style or change css class names for a component, this became a painful and bug prone task. This is why we have decided to only put HTML in razor file even if we know that razor inheritance is not working as expected*

NOTE: In SPEAK 1.2 using the technology preview layout, you can strongly type the View with a Model. The C# logic needed should be contained inside that object.

####HTML

Please refer to our [Html guidelines](html.md)

###CSS

Please follow [https://github.com/mdo/code-guide](https://github.com/mdo/code-guide)

####Additional Rule(s)

**Class naming conventions**

Never reference ```js-``` prefixed class names from CSS files. ```js-``` are used exclusively from JS files.

Use the ```is-``` prefix for state rules that are shared between CSS and JS.

### C# 

For C# part, please refer to the Sitecore guidelines.

