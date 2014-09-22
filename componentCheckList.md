#SPEAK Component CheckList

##Control

**Is the code located in the expected folder?**

*The code must be located in a folder that conforms to the rule contained to [component structure guideline](componentStructure.md).*

**Can multiple versions of the control run on the same page?**

*It must be possible to instantiate multiple controls on the same page. IDs must not be hardcoded and there must be no explicit references to global objects.*

Always make sure to create a test page scenario using at least twice the new component.

**Are all texts localized?**

*All visible text must the localized.*

**Does the control support data-binding?**

*Controls should be as dynamic as possible .*

**Is the Html output well-formed?**

*Output must be well-formed and conform to best practices. Attributes should use double-quotes.*

Please refer to the [HTML coding style](html.md)

**Are Html attributes Html encoded?**

*Html attributes should be Html attribute encoded to avoid invalid Html.*

**Does code use 2 spaces indent?**

*All code (.cshtml, .js, .ts, .css, .less etc) must use 2 spaces as indentation.*

**Do all database access go through ClientHost.Databases or ClientHost.Items?**
*Since SPEAK must be able to run in multiple databases, all database access must be routed through the ClientHost, so there is a single hook.*

##View (.cshtml)

**Is the View dependent on code (.cs) files?**

*As much code as possible should be present in the View file – not in a code file (.cs). For very complex control, it may make sense to have code files, but it should be avoid generally.*

From SPEAK 1.2 comes the supports of strongly typed model. Please, extend your model if you need to have complex logic. Please, always avoid to have database call in a Model or in a Razor view (retreiving parameters from the current item is accepted).

**Does the View use the standard helper functions?**

*SPEAK provides a number of helper functions, that reduce complexity in the View file. Examples are Sitecore().Controls().GetUserControl().*

**Does the View have a strongly typed model?**

*SPEAK 1.2 supports strongly typed models, which should always be used.*

**Does the View support nested components?**

*If the control supports nested controls, the HasNestedControls property should be set to true.*

**Does the View use the data-sc-component attribute to identify the control?**

*The control should be identified in the Html using the data-sc-component attribute and not a generic CSS selector. The View should set the data-sc-component attribute.*

**Is the control CSS class prefixed with “sc-“?**

If the control specifies a CSS class, the class name should be prefixed with “sc-“ to avoid clashes with other CSS libraries.

##Javascript (.js / .ts / .jsx)

**Are the properties declared in the model?**

*All public properties should be declared in the models initialize() method.*

**Is the code commented using JSDoc style?**

*All code should be commented using JSDoc style.*

**Does the code pass JSHint?**

*The code should conform to best practices and pass JSHint.*

Here is the configuration:

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

**Does the control follow best practices naming conventions?**

*Functions must be camelCased.*

**Does the code contain commented out code?**

*The code should not contain commented out code as this gives a bad impression.*

**(1.1 only) Does the control inherited from the proper base control?**

*The control can inherit from ComponentModel/View, ControlModel/View, ButtonControlModel/View, InputModel/View etc.*

**Does the code expose all fields from the parameters template?**

*All appropriate fields from the parameters template, should be exposed by the model.*

##Stylesheet (.css / .less)

**Is the code following the coding style?**

*We use the **[Boostrap Guidelines](https://github.com/mdo/code-guide)***

**Is the control themable?**

*The control should use the theming values from the SPEAK theme.*

##Code (.cs)

**Are the members marked up with Value Analysis attributes?**

*Members should be marked up with [NotNull] or [CanBeNull] attributes.*

**Are the members documents?**

*Member should have meaningful Xml comments.*

**Does the code pass StyleCop?**

*The code must pass StyleCop without errors. Please, refer to Sitecore settings.*

##View Item

**Is the Parameters Template specified?**

*All SPEAK controls must have a Parameters Template*

**Are placeholders specified?**

*All the placeholders that the control exposes, must be listed in the Place Holders field.*

**If appropriate, does the control specify a default placeholder?**

*The appropriate default placeholder should be specified in the Default Parameters collection.*

**Is the “Datasource Location” field set?**

The Data Source Location must the set to “PageSettings”.

**Is the “Datasource Template” field set?**

The Data Source Template must be set to the ID of the Parameters template.

##Parameters Template

**Do the appropriate fields have BindMode set?**

*Bindmode must be set for fields that do not use the standard read/write bind mode.*

**Do the fields have the appropriate field type?**

*Boolean fields must be checkboxes, integer fields must be integers, selections must be DropList etc.*

**Are the fields shared the appropriate way?**

*Visible text fields must be Versioned, other fields must be Shared.*

**Are the fields grouped into appropriate template sections?**

*Visible fields should be in “Appearance”, clicks and events should be in “Behavior”, data related fields should be in “Data” etc.*

**Do all fields specify the Short description field?**

*All fields should have help texts.*

**Field names must valid code identifiers.**

*As the field names are used in code, the field names should not contain spaces or illegal characters.*