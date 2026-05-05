---
title: "Design patterns and development strategies"
url: "https://www.selenium.dev/documentation/test_practices/design_strategies/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
<p>(previously located: <a href="https://github.com/SeleniumHQ/selenium/wiki/Bot-Style-Tests">https://github.com/SeleniumHQ/selenium/wiki/Bot-Style-Tests</a>)</p>
<h2 id="overview">Overview</h2>
<p>Over time, projects tend to accumulate large numbers of tests. As the total number of tests increases,
it becomes harder to make changes to the codebase &mdash; a single &ldquo;simple&rdquo; change
may cause numerous tests to fail, even though the application still works properly.
Sometimes these problems are unavoidable, but when they do occur you want to be up
and running again as quickly as possible. The following design patterns and strategies
have been used before with WebDriver to help make tests easier to write and maintain.
They may help you too.</p>
