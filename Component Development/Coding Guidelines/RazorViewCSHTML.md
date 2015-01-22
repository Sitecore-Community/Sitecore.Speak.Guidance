---
layout: default
title: Code Guidelines for Razor Views 
---


The following guidelines apply to CSHTML for components.

- Follow the All Language Styling guidelines.

- Follow the Boostrap coding guidelines.

- Do not close the void element.  For example, write `<br>` not `<br />`.

- Use pure HTML and use HTML elements as intended, for example, use `<a>` elements for links, not `<div onclick="...>`.

- Use tools such as the [W3C HTML Validator](http://validator.w3.org/nu/) to verify HTML.

- Use standard Sitecore helper functions, such as `Sitecore().Controls().GetUserControl()`, to reduce complexity in the View file.

- Use a strongly typed model (except in Core 1.1 components).

- Use double quotes for attribute values.

- Only use entity references for characters with special meaning.  For example, do use `&nbsp;` for a non-breaking space character, do use €, not `&eur;`.

- Strictly keep structure (markup), presentation (styling), and behavior (scripting) separate and keep interaction between all three to a minimum.

- Put HTML in the .CSHTML file, never in C#.

- Provide alternative access for multimedia.

- Use a new line for every block, list, or table element and indent every such child element.

- Put as much C# code in the CSHTML file as possible.  Only use a separate C# file for very complex controls.

- Always use a strongly typed model (except for Core 1.1 components).

- Avoid having database calls in the Model or Razor view.

- Prefix the component CSS class with `sc-`.

- Set HasNestedControls to true when the view supports nested components.

- Use the `data-sc-component` attribute to identify the component.