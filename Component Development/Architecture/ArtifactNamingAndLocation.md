---
layout: default
title: Artifact Naming and Location
---

The following guidelines apply to all components.

- Use PascalCase naming for all files, items, and component properties.

- Always try to use meaningful names for components, properties, events, and other artifacts that require a name.

- Components and property names implemented by Sitecore require approval from the SPEAK product manager and SPEAK gatekeeper.

- All files related to a component must have the same name and case:

    NameOfComponent.cshtml  
    NameOfComponent.js  
    NameOfComponent.css

- Components generally require the following artifacts:

    + A Razor file (*NameOfComponent.cshtml*)  
    + A Javascript file (*NameOfComponent.js*)
    + A Less file (*NameOfComponent.less*)
    + A generated Stylesheet (*NameOfComponent.css*)
    + A View Rendering item (*NameOfComponent*)
    + A Parameters Template (*NameOfComponent Parameters*)

## Positioning Component Files ##

- Place the component files in a component related folder following the existing component library folder structure in the file system.

- The location of component files for components in the SPEAK Business Component Library require approval from the SPEAK product manager and SPEAK gatekeeper.

## Positioning Component Items ##

- Place the View Rendering item in an appropriate folder following the existing component library folder structure in the content tree.

- The location of component items for components in the SPEAK Business Component Library require approval from the SPEAK product manager and SPEAK gatekeeper.

- Place the Parameters Template as a direct child of the View Rendering item.

- Place any additional component related items or templates as direct children of the component's View Rendering item.

- Place any items or templates shared by multiple components in an appropriate folder in the **/sitecore/client/Business Component Library/System** folder.
