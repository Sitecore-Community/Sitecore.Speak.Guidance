---
layout: default
title: Component Settings
---

1. Always provide a meaningful Id for components when you add them to the page definition item's Layout Details.  For example, use **OKButton**, not **Button1**.

1.  Never hard-code visible text in the component properties.  Always create a component settings item to store the text and reference the component settings item from the component's DataSource property.  This ensures localization of all visible text.
