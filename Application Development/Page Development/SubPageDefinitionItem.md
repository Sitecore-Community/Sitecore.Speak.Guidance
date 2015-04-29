---
layout: default
title: Subpage Definition Conventions
---

The following guidelines apply to business applications created by Sitecore for release as part of the Sitecore platform.

## Subpage ##

Subpage represents a set of components that are loaded separately from the server and embedded into a page.

**LoadOnDemandPanel** and **Repeater** controls render subpages.

1.	Use **Speak-BasePage** template when creating a new subpage.

1.	Use **Speak-EmptyLayout** for subpages.

1.	Include a **SubPageCode** component in the subpage definition item's Layout Details.
