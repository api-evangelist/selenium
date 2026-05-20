---
title: "Internet Explorer Driver Internals"
url: "https://www.selenium.dev/documentation/ie_driver_server/internals/"
date: "Mon, 01 Jan 0001 00:00:00 +0000"
author: ""
feed_url: "https://www.selenium.dev/index.xml"
---
Client Code Into the Driver We use the W3C WebDriver protocol to communicate with a local instance of an HTTP server. This greatly simplifies the implementation of the language-specific code, and minimzes the number of entry points into the C++ DLL that must be called using a native-code interop technology such as JNA , ctypes , pinvoke or DL . Memory Management The IE driver utilizes the Active Template Library (ATL) to take advantage of its implementation of smart pointers to COM objects.
