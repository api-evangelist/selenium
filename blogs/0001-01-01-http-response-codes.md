---
title: "HTTP response codes"
url: "https://www.selenium.dev/documentation/test_practices/discouraged/http_response_codes/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
For some browser configurations in Selenium RC, Selenium acted as a proxy between the browser and the site being automated. This meant that all browser traffic passed through Selenium could be captured or manipulated. The captureNetworkTraffic() method purported to capture all of the network traffic between the browser and the site being automated, including HTTP response codes.
