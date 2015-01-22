---
layout: default
title: Code Guidelines for JavaScript
--- 

The following guidelines apply to JavaScript for components.

## General Guidelines 

- Follow the All Language Styling guidelines.

- Avoid exposing the Global Object.

    + Do not use the Window object.  
    + Use RequireJS to express dependencies between JavaScript modules.  
.
- Use regular assignment to assign value to properties.

    + Get and Set work, but are not as readable.  
.
- Use the $ prefix for jQuery objects.

- Use camelCase when naming functions and variables

- Comment all code using JSDoc style.

- Do check in "commented out" code.

## Component-Specific Guidelines 

- The model should expose all appropriate parameters.

- Declare all public properties in the model's `initialize()` method.

- Since manipulating the DOM is slow, always separate DOM manipulation code from other code and ensure that you manipulate the DOM only once.

- Create helper functions for manipulating the DOM.

- Use properties when data binding can express a change, and/or to express values in the components parameters item.

- Use events when unable to use data binding or require more complex processing than data binding supports.

- Code must pass JSHint validation using the following configuration:

```
    {  
        curly: true,
        eqeqeq: true,
        immed: false,
        latedef: true,
        quotmark: "double",
        noarg: true,
        forin: true,
        newcap: true,
        sub: true,
        undef: false,
        boss: true,
        strict: false,
        unused: false,
        eqnull: true,
        node: true,
        browser: true,
        expr: "warn"
      }
``` 

- Only reference components from PageCode or other components.

  + Use an event emitter to communicate between a component and a custom module.

