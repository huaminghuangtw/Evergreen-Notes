---
title: URL_Schemes
created: 2024-11-18T10:16:50
modified: 2026-01-13T10:08:30
---

URL Schemes (= [Deep Linking](https://en.wikipedia.org/wiki/Deep_linking) = [x-callback-url](https://x-callback-url.com/)) is a hyperlink that links to a specific, generally searchable or indexed, piece of web content on a website (e.g., “http://example.com/path/page”), rather than the website’s home page (e.g., “[http://example.com](http://example.com/)”)

x-callback-url is originally for handling errors and communication between different apps. Using x-callback-url, _source_ apps can launch other apps passing data and context information, and also provide parameters instructing the _target_ app to return data and control back to the source app after executing an action.

URLs are structured as follows:

> `scheme://user:password@host:port/path?query#fragment`

* iOS Settings
	* [iOS Settings URLs](https://github.com/FifiTheBulldog/ios-settings-urls/blob/master/settings-urls.md)
	* [Complete List of iOS URL Schemes for Apple Settings](https://medium.com/@contact.jmeyers/complete-list-of-ios-url-schemes-for-apple-settings-always-updated-20871139d72f)
	* [FifiTheBulldog/ios-settings-urls: A collection of iOS Settings URLs](https://github.com/FifiTheBulldog/ios-settings-urls)
* iPhone Shortcuts
	* Open Shortcuts App: `shortcuts://`
	* Open shortcut: `shortcuts://open-shortcut?name=Shortcut%20Name`
	* Create new shortcut: `shortcuts://create-shortcut`
	* Run shortcut: `shortcuts://run-shortcut?name=Shortcut%20Name`
		* with clipboard as input: `shortcuts://run-shortcut?name=Shortcut%20Name&input=clipboard`
		* with text as input: `shortcuts://run-shortcut?name=Shortcut%20Name&input=Hi%20There`
* [Apple Reminders](https://www.reddit.com/r/shortcuts/comments/bc5h9a/reminders_url_scheme/)

	```
	x-apple-reminderkit://REMCDReminder/{UUID of Reminder}
	```

* Apple Apps
	* [Complete List of iOS URL Schemes for Apple Apps](https://medium.com/p/800c64f450f)
* Third-Party Apps
	* [Complete List of iOS URL Schemes for Third-Party Apps](https://medium.com/p/5663ef15bdff)
