---
layout: default
title: Page Definition Conventions
---



The following guidelines apply to applications created by Sitecore for release as part of the Sitecore platform.

1. Always use one of the predefined page branches when creating a new page (DashboardPage, ListPage, or TaskPage).

1. Always use the Speak-Layout for all SPEAK Pages.

1. Customers and Partners may choose to create their own SPEAK Layout (although we do not recommend it).  If you create your own layout, be sure to add to following lines at appropriate locations (refer to the Speak-Layout for an example):

    <html data-sc-app>
    
    @Html.Sitecore().Placeholder("Page.Code")
    
    @Html.Sitecore().Placeholder("Page.Body")
    

1. Always create a PageSettings item based on the PageSettings template underneath the page definition item.  Include all page specific settings items underneath this item.  Store settings items that multiple pages reference in the application's **<AppName\>/Settings/System** folder.

1. Always include a PageCode component in the page definition item's Layout Details (included automatically when you use a predefined page branch as indicated above).

1. Use pre-defined layout structures whenever possible.  If an appropriate layout structure does not exist, request one from the UX and SPEAK Teams.

1. Use the Page-StyleSheet-File item to add a CSS file to your page. 

1. Use the Page-Script-File item to add a JavaScript file to your page.  



