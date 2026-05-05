---
title: "Selenium components"
url: "https://www.selenium.dev/documentation/overview/components/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
<p>Building a test suite using WebDriver will require you to understand and
effectively use several components. As with everything in
software, different people use different terms for the same idea. Below is
a breakdown of how terms are used in this description.</p>
<h3 id="terminology">Terminology</h3>
<ul>
<li><strong>API:</strong> Application Programming Interface. This is the set of &ldquo;commands&rdquo;
you use to manipulate WebDriver.</li>
<li><strong>Library:</strong> A code module that contains the APIs and the code necessary
to implement them. Libraries are specific to each language binding, eg .jar
files for Java, .dll files for .NET, etc.</li>
<li><strong>Driver:</strong> Responsible for controlling the actual browser. Most drivers
are created by the browser vendors themselves. Drivers are generally
executable modules that run on the system with the browser itself,
not the system executing the test suite. (Although those may be the
same system.) NOTE: <em>Some people refer to the drivers as proxies.</em></li>
<li><strong>Framework:</strong> An additional library that is used as a support for WebDriver
suites. These frameworks may be test frameworks such as JUnit or NUnit.
They may also be frameworks supporting natural language features such
as Cucumber or Robot Framework. Frameworks may also be written and used for
tasks such as manipulating or configuring the system under test, data
creation, test oracles, etc.</li>
</ul>
<h3 id="the-parts-and-pieces">The Parts and Pieces</h3>
<p>At its minimum, WebDriver talks to a browser through a driver. Communication
is two-way: WebDriver passes commands to the browser through the driver, and
receives information back via the same route.</p>
