---
title: "Backing Selenium with WebDriver"
url: "https://www.selenium.dev/documentation/legacy/selenium_2/emulation/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
(Previously located: https://github.com/SeleniumHQ/selenium/wiki/Selenium-Emulation ) Backing Selenium with WebDriver The Java and .NET versions of WebDriver provide implementations of the existing Selenium API. In Java, it is used like so: // You may use any WebDriver implementation. Firefox is used here as an example WebDriver driver = new FirefoxDriver(); // A "base url", used by selenium to resolve relative URLs String baseUrl = "http://www.google.com"; // Create the Selenium implementation Selenium selenium = new WebDriverBackedSelenium(driver, baseUrl); // Perform actions with selenium…
