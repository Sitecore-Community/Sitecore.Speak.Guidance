---
layout: default
title: Custom Component Guidelines
---

The following guidelines apply to business applications created by Sitecore for release as part of the Sitecore platform.

1. Only use components provided in the SPEAK Business Component Library (BCL).

1. If the BCL does not contain any components that can come close to your application's requirements, contact the UX Team and SPEAK Product Manager with a ***new component request***.  The UX Team and SPEAK Product Manager will work with you to create a plan.

1. If an existing component comes close to your application's requirements, but does not have a specific behavior your application requires, contact the UX Team and SPEAK Product Manager with a ***change request***.

1. If your change request is rejected, your application must use the existing components. The UX Team and SPEAK Product Manager will provide guidance. 

1. If your change request is approved, you may be asked to create a local custom component to implement the required behavior locally, either to allow progress on your application while the SPEAK Team implements the change, or to contribute your implementation of the change to the BCL after approval of the implementation by the SPEAK Gatekeeper.

## Local Custom Components Guidelines##

You should create a local custom component for your application in the following situations:

- Your team has submitted a component change request and were requested to implement the change locally.

- Your team requires the same functionality implemented in another application as a local custom component.

- Your team has submitted a new component request and were requested to implement the new component locally.

When creating a local custom component, follow these guidelines.

### Creating a Local Copy of a Component ###

1. When creating a local copy of an existing component (either from the BCL or another application), copy the existing implementation files and items to your application development environment.

1. Rename the files and items to include your application name as a prefix to the original component.  For example, if your application name is "MyApp" and the original component name is "Button", the new name should be "MyAppButton".

1. Recreate the original BCL item definition structure for the component definition items underneath your application's Settings folder.

1. Recreate the original file system folder and file structure for the component definition files underneath your application's file structure.

1. Follow all Component Development guidelines when making the required changes in the component definition items and files.

### Creating a New Local Component ###

1. Choose a descriptive name for the component and include the name of your application as a component name prefix.  For example, if your application name is "MyApp" and the new component implemented a Rich Text Editor, the name should be "MyAppRichTextEditor".

1. Agree on a component library location for the new component with the SPEAK and UX Teams and create the required item structure underneath your application's Settings folder.

1. Create a corresponding file system folder and file structure for the component definition files underneath your application's file structure.

1. Follow all Component Development guidelines when creating the new component.
