#SPEAK Guidelines

In order to make SPEAK open to internal developers, we needed to define guidelines in order to accept pull-requests.

Those guidelines must be strictly followed by the people who wants to collaborate.

This guideline is a living guideline and is open to suggestions and improvements. You are welcome to raise issues and propose your pull-requests for the SPEAK collaboration guidelines.

**Acronym**

SPEAK is an acronym for Sitecore Process Enable Accelerator Kit.
BCL is an acronym for Business Component Library.


**SPEAK typo**

When writing about SPEAK, you should always use capital case. On social media, "SPEAKui" is also acceptable to refer to the SPEAK twitter account.

There are exceptions to that rule.

- In Javascript, the variable will be called Speak (PascalCase) even if it is an acronym because in JavaScript full capital case for a variable or a name-space means a constant (like Math.PI).
- When naming our layouts or items in SPEAK, we have also used the PascalCase notation. As we found that SPEAK-layout was an ugly name, we went for Speak-layout. Normally only the SPEAK project and the BCL should have items containing the name SPEAK.


**Disclaimer**

This guideline is new and some part of the current is not entirely reflecting what is described below. If it is the case, it would be kind of you to re-format it following the current guidelines.

##Filling Issues

The github issue list is for bugs, not discussions. If you have a question you want to ask you have many alternatives:

- [Stack Overflow](http://stackoverflow.com/questions/tagged/speakui)
- [SPEAK Forum](http://sdn.sitecore.net/Forum/ShowPost.aspx?PostID=61867)
- [SPEAK Mailing list](mailto:scspeak@sitecore.net)

When filling issues, please follow [the bug filling templates](/bug.md). The best way to get your bug fixed is to be as detailed as you can be about the problem. Providing a minimal project (or a URL accessible internally) which steps to reproduce the problem is ideal. Here are questions you can answer before you fire a bug to make sure you are not missing any important information.

1. Did you read the documentation?
2. Did you include the snippet of broken code in the issue (or at least a print screen)?
3. Can you reproduce the problem in a brand new project, or a brand new page?
4. What are the **EXACT** steps to reproduce this problem?
 
##Coding guidelines

**SPEAK component**

Please read our [SPEAK component guideline](component.md)

**SPEAK page**

Please read our [SPEAK page guideline](page.md)

**SPEAK application**

Please follow, the [Sitecore Business Application guideline](speak.md) to structure your application and name your items correctly if it is built using SPEAK.

##Contributing

###Project Worfkflow

*draft mode* 

Our workflow is loosely based on [Github Flow](http://scottchacon.com/2011/08/31/github-flow.html). We actively develop in the **master** branch. This means that all pull requests by contributors need to be developed and submitted on the master branch. If you need to fix an error for a specific version of SPEAK. You can find it as a "tag". If you need a fix for an anterior release, please contact the Sitecore Support. The master branch created a Symphony package for the Sitecore Platform on a nightly basis. This means that anything committed to master could go to the next release of Sitecore.

###Issue management

*draft mode*

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

*draft mode*

Make sure you can build the code. Familiarize yourself with the project workflow and our coding conventions. If you don't know what a pull request is read this https://help.github.com/articles/using-pull-requests.

Before submitting a feature or substantial code contribution please discuss it with the team and ensure it follows the product roadmap. 

Note that all code submissions will be rigorously reviewed and tested by the Sitecore SPEAK Team, and only those that meet an extremely high bar for both quality and design/roadmap appropriateness will be merged into the source. [Don't "Push" Your Pull Requests](https://www.igvita.com/2011/12/19/dont-push-your-pull-requests/)

##Testing

TO BE DONE

##Best Practices

TO BE DONE

##FAQ

PLease refer to [link to FAQ TBDefined]

##SPEAK Team and Resources

###Internal Contact Point

TBD

###External Contact Point

TBD

###Team members

TBD


##Social

You can follow us on twitter [https://twitter.com/speakui](https://twitter.com/speakui)