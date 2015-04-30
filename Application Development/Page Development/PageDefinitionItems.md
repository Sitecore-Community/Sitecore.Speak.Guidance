---
layout: default
title: Page definition conventions
---



The following guidelines apply to _applications created by Sitecore for release as part of the Sitecore platform_.

1. Always use one of the predefined page branches when creating a new page (**DashboardPage**, **ListPage**, or **TaskPage**).

1. Always use the **Speak-Layout** for all SPEAK pages.

1. Customers and partners may choose to create their own SPEAK layout (although we do not recommend it).  If you create your own layout, be sure to add to following lines at appropriate locations (refer to the Speak-Layout for an example):
>    &lt;html data-sc-app&gt;
>    @Html.Sitecore().Placeholder("Page.Code")  
>    @Html.Sitecore().Placeholder("Page.Body")  


4. Always create a **PageSettings** item based on the **PageSettings** template underneath the page definition item.  Include all page specific settings items underneath this item.  Store settings items that multiple pages reference in the application's **&lt;AppName&gt;/Settings/System** folder.

5. Always include a PageCode component in the page definition item's Layout Details (included automatically when you use a predefined page branch as indicated above).

6. Use pre-defined layout structures whenever possible.  If an appropriate layout structure does not exist, request one from the UX and SPEAK teams.

7. Use the **Page-StyleSheet-File** item to add a CSS file to your page.

8. Use the **Page-Script-File** item to reference a 3rd party JavaScript file from your page.  
