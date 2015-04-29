---
layout: default
title: Code Guidelines for C#
---

The following guidelines apply to C# code for components.

- Follow the All Language Styling guidelines.

- Use StyleCop with standard Sitecore settings.

- Mark members with `[NotNull]` and `[CanBeNull]`

- Include meaningful XML comments for all members.

- Never manipulate (add HTML, set attributes etc.) HTML directly in .CS files - only include HTML in the .CSHTML files.
