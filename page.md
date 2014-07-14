#SPEAK Page Coding Style

1) A SPEAK Page should always have a PageSettings Item.

This PageSettings item should contain all the items specific to the page. In case of shared item for pages, you should move them under the Common/System folder.

2) A SPEAK Page should always try to use the Speak-Layout.

3) A SPEAK Page must have a PageCode (even empty)

4) Always try to give meaningful name for your component.

5) Never hardcode string when you set Text for a parameter. Use the Datasource property of the Component and point it to an Item that can be localized.

6) Re-use the predefined structure as much as possible.

SPEAK has defined some structure like ApplicationContentM, ApplicationContentMI,...

They are located under /sitecore/client/Business Component Library/Layouts/Renderings/Structures/

7) Use the Page-StyleSheet-File item to add a css file in your page. That Item must be placed under the PageSettings.

8) Use the Page-Script-File item to add a javascript file specific to your page (please avoid this and contact SPEAK Team in case of doubt).

9) In case of complex page structure, create a custom component without JavaScript.

If you have a complicated page structure and you end up creating lots of Border, Row, ColumnPanel, create a custom component for your Page(s) which only contains HTML with placeholder. This will safe you time and increase the performance.

If you are using the BCL, you are welcomed to use the bootstrap classes for creating your Grid.  