---
title: "File downloads"
url: "https://www.selenium.dev/documentation/test_practices/discouraged/file_downloads/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
Whilst it is possible to start a download by clicking a link with a browser under Selenium’s control, the API does not expose download progress, making it less than ideal for testing downloaded files. This is because downloading files is not considered an important aspect of emulating user interaction with the web platform. Instead, find the link using Selenium (and any required cookies) and pass it to a HTTP request library like curl .
