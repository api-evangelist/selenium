---
title: "Grid endpoints"
url: "https://www.selenium.dev/documentation/grid/advanced_features/endpoints/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
Grid Grid Status Grid status provides the current state of the Grid. It consists of details about every registered Node. For every Node, the status includes information regarding Node availability, sessions, and slots. curl --request GET 'http://localhost:4444/status' Delete session Deleting the session terminates the WebDriver session, quits the driver and removes it from the active sessions map.
