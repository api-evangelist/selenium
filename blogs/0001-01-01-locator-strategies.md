---
title: "Locator strategies"
url: "https://www.selenium.dev/documentation/webdriver/elements/locators/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
<p>A locator is a way to identify elements on a page. It is the argument passed to the
<a href="https://www.selenium.dev/documentation/webdriver/elements/finders/">Finding element</a> methods.</p>
<p>Check out our <a href="https://www.selenium.dev/documentation/test_practices/encouraged/">encouraged test practices</a> for tips on
<a href="https://www.selenium.dev/documentation/test_practices/encouraged/locators/">locators</a>, including which to use when and
why to declare locators separately from the finding methods.</p>
<h2 id="traditional-locators">Traditional Locators</h2>
<p>Selenium provides support for these 8 traditional location strategies in WebDriver:</p>
<table>
 <thead>
 <tr>
 <th>Locator</th>
 <th>Description</th>
 </tr>
 </thead>
 <tbody>
 <tr>
 <td>class name</td>
 <td>Locates elements whose class name contains the search value (compound class names are not permitted)</td>
 </tr>
 <tr>
 <td>css selector</td>
 <td>Locates elements matching a CSS selector</td>
 </tr>
 <tr>
 <td>id</td>
 <td>Locates elements whose ID attribute matches the search value</td>
 </tr>
 <tr>
 <td>name</td>
 <td>Locates elements whose NAME attribute matches the search value</td>
 </tr>
 <tr>
 <td>link text</td>
 <td>Locates anchor elements whose visible text matches the search value</td>
 </tr>
 <tr>
 <td>partial link text</td>
 <td>Locates anchor elements whose visible text contains the search value. If multiple elements are matching, only the first one will be selected.</td>
 </tr>
 <tr>
 <td>tag name</td>
 <td>Locates elements whose tag name matches the search value</td>
 </tr>
 <tr>
 <td>xpath</td>
 <td>Locates elements matching an XPath expression</td>
 </tr>
 </tbody>
</table>
<h2 id="creating-locators">Creating Locators</h2>
<p>To work on a web element using Selenium, we need to first locate it on the web page.
Selenium provides us above mentioned ways, using which we can locate element on the
page. To understand and create locator we will use the following HTML snippet.</p>
