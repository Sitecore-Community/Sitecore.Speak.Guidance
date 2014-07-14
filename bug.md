### Title
*A short description of the bug that becomes the issue title*  

e.g. TabControl triggers and error when Tabs contain a Border container.

### Any functional impact

*Does the bug result in any actual functional issue, if so, what?*

e.g. If poll request starts working again, it recovers. Otherwise, it sends many requests per sec to the server.

### Contextual Information

- Sitecore Version
- SPEAK version
- Browser Type & Version
- OS.
- Current Project

e.g. Sitecore 8.0 rev. 140623, SPEAK 1.3 rev. 15054, IE 11, Windows 8.1. Project Nerva

### Minimal repro steps
*What is the smallest, simplest set of steps to reproduce the issue. If needed, provide a project that demonstrates the issue.*  

1. Create a SPEAK Page
2. Add a TabControl in the Page
3. Create one Tab for the TabControl
4. Inside that Tab, create a Border
5. Load the Page and you should get the error

### Expected result
*What would you expect to happen if there wasn't a bug*  

e.g. The border should show and I should not get any Javascript Error

### Actual result
*What is actually happening*  
e.g. I got the error "cannot bind the same component more than once" in my chrome dev tool console.

### Further technical details
*Optional, details of the root cause if known*  
e.g. It looks like the TabControl does not support any kind of other container inside itself. If I remember well, we have a "hasNested" attribute defined which does not seem to be set to true. When I tried to set it to true, it looks like the error disappear. Could you please give me confirmation and fixing for the next nightly build. 