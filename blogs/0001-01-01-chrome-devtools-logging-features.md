---
title: "Chrome DevTools Logging Features"
url: "https://www.selenium.dev/documentation/webdriver/bidi/cdp/logging/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
While Selenium 4 provides direct access to the Chrome DevTools Protocol, these methods will eventually be removed when WebDriver BiDi implemented. Console Logs Java Python CSharp Ruby JavaScript Kotlin (( HasLogEvents ) driver ). onLogEvent ( consoleEvent ( e -> messages . add ( e . getMessages (). get ( 0 )))); View Complete Code View on GitHub /examples/java/src/test/java/dev/selenium/bidi/cdp/LoggingTest.java Copy Close package dev.selenium.bidi.cdp ; import static org.openqa.selenium.devtools.events.CdpEventTypes.consoleEvent ; import dev.selenium.BaseTest ; import java.time.Duration ;…
