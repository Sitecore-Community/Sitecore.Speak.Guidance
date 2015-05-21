---
layout: default
title: Baseline Component Functionality
---


All components must provide this baseline functionality:

- Support multiple instances of the same component on a single page.
    + No hard coded IDs.
    + No  explicit references to global objects.
    + Create a test scenario with at least two instances of the component on the page.  
- Support multilanguage applications (all visible text must be localizable).
- Generate well-formed HTML.
    + Use double-quotes for all attributes.
    + Always encode HTML attributes.
    + Follow the HTML coding style.  
- Support data-binding for all appropriate properties.
- Always access the database via `ClientHost.Databases` or `ClientHost.Items`.
- Encode all untrusted data to prevent XSS attacks.
- Do not expose any sensitive data.
