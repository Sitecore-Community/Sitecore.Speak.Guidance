---
layout: default
title: Component Parameters Template Guidelines
---


The following guidelines apply to all components.

- Create appropriate field sections for your parameters (such as Appearance, and so on).

- Always use an appropriate file type for parameters.

  + Use `Single-Line Text` fields which support binding.
  + Use `Checkbox` fields for Boolean parameters.
  + Use `Integer`fields for integer parameters.
  + Use `DropList`fields for parameters which support selection.  
.

- Use a GUID (not a path) when you restrict the DataSource for a parameter to a specific folder.

- Specify `Versioned` fields for parameters that contain visible text and `Shared` fields for all other parameters.

- Create a `__Standard Values` item for the Parameters Template and set default values for parameters there.

- Set the bindmode in the `Source` field (in the `Data` field section) if the parameter does not use standard read/write binding.

- Set an appropriate help text in the `__Short description` field (in the `Help` field section).

