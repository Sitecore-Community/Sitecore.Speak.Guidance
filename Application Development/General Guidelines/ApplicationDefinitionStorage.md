---
layout: default
title: Application Definition Storage
---

The following guidelines apply to business applications created by Sitecore for release as part of the Sitecore platform.

## Application Definition Items ##

1. Whenever possible, keep all definition items for an application in a single folder. This includes all page definition items, templates, component settings items, and so on.  Make exceptions only when required by Sitecore, such as for dictionary definition items.

1. Create the application folder in the Core database, under the **/sitecore/client/Applications** folder.

1. The application folder name should match the application name.

1. Set the application folder item's icon to the UX approved application icon.

1. Create the application Dashboard page, which is the application's default initial page and is also known as the root page, directly under the application folder. Use the name **Dashboard** and the **/templates/branches/applications/DashboardPage** branch.

1. Create all other pages accessible from the Dashboard page as sub-items under the Dashboard page.

1. Create a **Settings** folder directly under the application folder.  Create folders under the Settings folder to store non-page related definition items, such as for common text, templates, field value enumerations, and so on.  Give these folders appropriate names, such as Templates or Common Text.

1. Add an application shortcut that links to the application dashboard page to the Launchpad with a UX approved icon and title.

## Application Definition Files ##

1. Create a folder with the name of your application underneath the **...\Website\sitecore\shell\client\Applications** folder.

1. Create a folder structure underneath this folder with folders for each page that requires page code or other definition files.
