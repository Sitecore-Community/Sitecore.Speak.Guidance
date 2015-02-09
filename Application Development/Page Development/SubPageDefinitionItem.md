---
layout: default
title: Sub-page Definition Conventions
---

The following guidelines apply to business applications created by Sitecore for release as part of the Sitecore platform.

## Sub-page ##

Sub-page represents a set of components that are loaded separately from the server and embedded into a page.
LoadOnDemandPanel and Repeater controls render sub-pages.

1.	Use Speak-BasePage template when creating a new sub-page.
1.	Use Speak-EmptyLayout for sub-pages.
1.	Include a SubPageCode component in the sub-page definition item's Layout Details.
