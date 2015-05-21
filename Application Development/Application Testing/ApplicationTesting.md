---
layout: default
title: Testing SPEAK Applications
---

The following guidelines apply to applications *created by Sitecore for release as part of the Sitecore platform*.

###Testing Framework

- Test SPEAK applications using **UTF.SPEAK**.

	+ **UTF.SPEAK** is based on **.NET UTF**.
	+ **UTF.SPEAK** uses [Selenium WebDriver](http://docs.seleniumhq.org/) to provide support for cross-browser testing.  


- Use the **NUnit** testing framework (other frameworks, such as MSTest and XUnit, may work but are not officially supported).

####Cross Browser Testing

- Selenium supports **Mozilla Firefox** by default.

- Use [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) to run tests in **Google Chrome**.

- Use [Explorer Driver Server](https://code.google.com/p/selenium/wiki/InternetExplorerDriver) to run tests in **Internet Explorer**.

####SPEAK Application Wrapper Project

An "Application Wrapper" project uses SPEAK Component wrappers from UTF.SPEAK to simulate user behaviour.  

- Create a (.Net Framework v4.0+) C# Class Library project for your Application Wrapper project.

- Reference the `UTF.dll` and the `UTF.SPEAK.dll`.

- If your application contains custom components that require custom component wrappers, add a reference to the `WebDriver.dll` and `WebDriver.Support.dll`.

- Place the `WebDriver.dll` and `WebDriver.Support.dll` (even if you do not reference them) in the same folder as compiled .dll files (usually the `\bin\` folder of Application Wrapper project).

- Place the `HelperWebService.asmx` file in the Sitecore `\Website`\ folder.

- Place the `HelperWebService.dll` file in the Sitecore `\bin` folder.

####SPEAK Application Wrappers

- Create an "application wrapper" for each page in your application.

- Use either **`Page`** or **`FramePage`** as a base class for your application wrapper.

	+ For pages which open in a page use the **`Page`** class.
	+ For pages which open in an iframe use the **`FramePage`** class.  
	.

- Use properties to initialize the SPEAK component wrapper(s) on the page.

	+ All SPEAK components in the standard component library have UTF.SPEAK component wrapper.  
.

- To initialize a SPEAK component wrapper on a page use the `SpeakRepository.Instance.GetControl<T>()` method or the `Driver.GetSpeakControl<T>()` method.
For example:

        public SpeakAdvancedExpander AdvancedExpander
        {
            get { return  SpeakRepository.Instance.GetControl<SpeakAdvancedExpander>(); }
        }

- Use the SPEAK component's hierarchy scheme to locate nested controls.

	+ To work with nested controls use `NestedControls<T>()` method:

     `AdvancedExpander.GetNestedControl<SpeakListControl>()`

- Use the SPEAK component wrapper's properties and methods to interact with the SPEAK component on the page.

- Implement custom methods to simulate user activities on the page.

- Use `Context.HelperService` to work with the Sitecore API.

####Application Test Project Setup

An Application Test Project contains the UI auto-test for the SPEAK application.
It uses `UTF.dll`, `UTF.SPEAK.dll`, and Speak Application wrapper .dll.

- Create a (.Net Framework v4.0+) C# Class Library project for your Application Test project.

- Reference  `UTF.dll` and `UTF.SPEAK.dll`.

- Reference the SPEAK Application Wrapper .dll you created (described above).

- Place the `WebDriver.dll` and `WebDriver.Support.dll` (even if you do not reference them) in the same folder as compiled .dll files (usually the `\bin\` folder of Application Wrapper project).

- Place the `HelperWebService.asmx` file in the Sitecore `\Website`\ folder.

- Place the `HelperWebService.dll` file in the Sitecore `\bin` folder.

- Place IEDriverServer.exe and chromedriver.exe to `\bin` folder in order to run auto-test against IE and Chrome.

- Create a "Test Fixture" class derived from `UTF.TestFixtureBase`.

- Define test suite behavior using `[TestFixture(BrowserType.Browser)]`  attributes.

- Define an App.config file with instance name, browsers to run, HelperWebService folder, screen shot folder.
