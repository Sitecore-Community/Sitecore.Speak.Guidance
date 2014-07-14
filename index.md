#SPEAK Guidelines

In order to make SPEAK open to internal developers, we needed to define guidelines in order to accept pull-requests.

Those guidelines must be strictly followed by the people who wants to collaborate.

Those lines are also an "open" and subject to changes. You are welcome to raise issues and propose your pull-requests for the SPEAK collaboration guidelines.

**Disclaimer**

Note that this guideline is new and some part of the current is not entirely reflecting what is described below. If it is the case, it would be kind of you to re-format it following the current guidelines.

##Filling Issues

The github issue list is for bugs, not discussions. If you have a question you want to ask you have many alternatives:

- [Stack Overflow](http://stackoverflow.com/questions/tagged/speakui)
- [SPEAK Forum](http://sdn.sitecore.net/Forum/ShowPost.aspx?PostID=61867)
- [SPEAK Mailing list](mailto:scspeak@sitecore.net)

When filling issues, please follow [the bug filling templates](/big.md). The best way to get your bug fixed is to be as detailed as you can be about the problem. Providing a minimal project (or a URL accessible internally) which steps to reproduce the problem is ideal. Here are questions you can answer before you fire a bug to make sure you are not missing any important information.

1. Did you read the documentation?
2. Did you include the snippet of broken code in the issue (or at least a print screen)?
3. Can you reproduce the problem in a brand new project, or a brand new page?
4. What are the **EXACT** steps to reproduce this problem?
 
##Contributing

###Coding guidelines

**Backend**

We follow the [ASP.NET webstack coding guidelines](http://aspnetwebstack.codeplex.com/wikipage?title=CodingConventions)

**Client**

We follow the jQuery convention on how to write javascript except the 2 spaces for a Tab.

**Sitecore**

Please follow, the [Sitecore guideline](speak.md) to structure your SPEAK application and name your layout, items correctly. 


###Project Worfkflow

Our workflow is loosely based on [Github Flow](http://scottchacon.com/2011/08/31/github-flow.html). We actively develop in the **master** branch. This means that all pull requests by contributors need to be developed and submitted on the master branch. If you need to fix an error for a specific version of SPEAK. You can find it as a "tag". If you need a fix for an anterior release, please contact the Sitecore Support. The master branch created a Symphony package for the Sitecore Platform on a nightly basis. This means that anything committed to master could go to the next release of Sitecore.

###Issue management

**Tag Format**

- Bug - A bug
- PBI - Product Backlog Item (a feature), follow the PBI guideline to create appropriate change request.

Each week, the SPEAK committee decides which PBIs/Bugs need to be integrated into the SPRINT.

Here is the flow for your PBI/BUG:

- 1 - Ready

It means you have provided enough information PBI/Bug in order to be developed.

- 2 - Blocked

It means that your PBI/Bug has been integrated to our backlog.

- 3 - Working

It means one of our developer is currently working on it.

- 4 - Review

It means, this PBI/Bug is on review states.

- 5 - Done (open)

Bug/Feature has been "accepted" as final and is ready for verification (pushed to source)

- 5 - Done (close)

Bug/Feature has been "accepted" as final and has resolved the corresponding issue

###Submitting Pull requests

Make sure you can build the code. Familiarize yourself with the project workflow and our coding conventions. If you don't know what a pull request is read this https://help.github.com/articles/using-pull-requests.

Before submitting a feature or substantial code contribution please discuss it with the team and ensure it follows the product roadmap. 

Note that all code submissions will be rigorously reviewed and tested by the Sitecore SPEAK Team, and only those that meet an extremely high bar for both quality and design/roadmap appropriateness will be merged into the source. [Don't "Push" Your Pull Requests](https://www.igvita.com/2011/12/19/dont-push-your-pull-requests/)
