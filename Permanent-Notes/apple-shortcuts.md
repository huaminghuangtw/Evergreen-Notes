---
title: Apple Shortcuts
modified: 2026-11-12
---

# Overview

AppleScript ➞ Automator ➞ Shortcuts

[比較]

* iOS: Apple’s Shortcuts
* Android: Google’s Action Blocks

**Guiding principle:** keep automation simple and intuitive. If a workflow is complex, package it as a custom Shortcut and call it with the “Run Shortcut” action. This makes sharing and maintainability much easier.

# Actions

* “Take Screenshot” + “Extract Text from Image” (for OCR)
* Get “Item” from List → Options: “First Item”, “Last Item”, \*“Random Item”, “Item at Index”, “Items in Range”
* Get random items from List
	* **Single:** “Get Item from List” → Choose “Random Item”
	* **Multiple:** “Filter Files” → Choose “Random” in “Sort by” → Enable “Limit” → Select the number of random items you want to get
* “Is Charging” vs “Is Connected to Charger” (Get Battery Status)
	* **Former:** Is the device gaining battery charge?
	* **Latter:** Is the device connected to a charger that at least is slowing down the rate the battery drains?

	> For Optimized Battery Charging: being connected to a charger but not charging

* Shortcut icon: use the “Get Images from Input” action

## “Get Weather Forecast” (↔ “Get Current Weather”)

* **Hourly:** Retrieves results for the next 24 hours in a list of 25 items—the first represents the current conditions, followed by the forecasts for the next 24 hours.
	![](https://media.huam.ing/image/2118d91a37cb7dc5a696bd6b15147dce.webp)

* **Daily:** Retrieves results for the next 10 days in a list of 10 items.
	![](https://media.huam.ing/image/fe643d04ef2efb1bd50d7426f62665b8.webp)

# Data Types

## List

* Comma-separated text
* Each item is encoded

## Dictionary

* A great way of storing multiple pieces of information at once; in Shortcuts it is converted into a JSON plain-text object
* “Get Dictionary Value” → Options: “Value”, “All Keys”, “All Values”
	* Often: “Choose from List” + “All Keys”
		* **Tip:** “Choose from List” can also be used for a “Dictionary”!
			* Get “Value” for “Chosen Item → _**Name**_” from “Dictionary”

## Boolean

* How to use Boolean variables?
	* Method I: Type = Boolean → `If "myBooleanVar"`
	* Method II: Type = Text → `If "myBooleanVar" is Yes/No`

## Uniform Type Identifiers (UTIs)

[Apple’s Uniform Type Identifiers (UTIs)](https://en.wikipedia.org/wiki/Uniform_Type_Identifier)

* A framework used in macOS and iOS for identifying data types and file formats in a standardized and consistent way.
* Strings that uniquely identify types of data.
* Examples
	* Public UTIs
		* `public.text`
		* `public.image`
		* `public.json`
	* Private UTIs
		* `com.example.myapp.myformat`
		* `com.adobe.pd`
		* `com.apple.plist` = `com.apple.property-list`
		* `com.apple.shortcuts.action`

# Variables & Control Flow

* “Add to Variable” → List
	* **Tip:** “Repeat with each item” + “Text” → “Repeat Results” is already a list of “Text”, not need to use “Add to Variable” for each iteration → simplify code!
* Magic variables

# Triggering a Shortcut

## Run Shortcut action vs URL scheme

* **Tip:** If you’d like to run one shortcut from another shortcut, use the `Run Shortcut` action instead of a URL scheme. You should only run shortcuts with a URL if you’re integrating from another app outside of Shortcuts (e.g., in a shell script, in Terminal)
* _Run Shortcut_ vs _URL Scheme_
	* Difference
		* _URL Scheme_ requires to open the Shortcuts app, while _Run Shortcut_ doesn’t.

## URL schemes

* “Open X-Callback URL” (= [URL_Schemes](URL_Schemes.md))
	* Allow you to go beyond “Open App” in Shortcuts
	* They are helpful in the Shortcuts app when the App itself doesn’t have any Shortcut Actions support available by default
* [Run a shortcut using a URL scheme on iPhone or iPad](https://support.apple.com/en-gb/guide/shortcuts/apd624386f42/ios)
	* Import Shortcut: `shortcuts://import-shortcut/?url=[url]&name=[name]`
		* Parameters:
			* url: download url for a `.shortcut` file
			* name (optional): name for shortcut, defaults to shortcut filename
			* silent (optional): `true` to import without opening the shortcut, `false` by default to open and display the shortcut to the user
		* Example: `shortcuts://import-shortcut/?name=Awesome%20Shortcut&url=https%3A%2F%2Fdownloadwebsite.com`
	* Open Shortcut:
		* `shortcuts://` to launch app to last-used state
		* `shortcuts://create-shortcut` to create a new shortcut
		* `shortcuts://open-shortcut?name=[name]` to open the app to the shortcut of a given name
	* Run Shortcut: `shortcuts://run-shortcut`
		* ⭐️ Query parameters:
			* name: string name for shortcut
			* input (optional): initial input into the shortcut, a text string or the word `clipboard` to use the contents of the clipboard
		* Example: `shortcuts://run-shortcut/?name=Shortcut%20to%20Run`
	* `shortcuts://x-callback-url/run-shortcut?name=[name]&x-success=[your-application-url]`
		* Callback URL work with 3 parameters:
			* `x-success` — To handle Successful execution
			* `x-cancel` — To handle interruptions in execution
			* `x-error` — To handle errors in execution
	* Open the Shortcuts Gallery
		* `shortcuts://gallery`
	* Search the Shortcuts Gallery
		* `shortcuts://gallery/search?query=[query]`
* [比較]
	* `Open X-Callback URL`: If your Shortcut has to wait for response
	* `Open URLs`: If your Shortcut doesn’t have to wait for response

## Keyboard hotkeys

Two ways to set and view binding keyboard hotkeys for Shortcuts

1. Settings → Keyboard → Keyboard Shortcuts → Services → Shortcuts
2. Shortcuts App on macOS → “Quick Actions” in the sidebar

# Command Line

There are only four subcommands in the command-line (CLI) version of `shortcuts://run-shortcut` from Terminal: `list`, `run`, `view`, `sign`

* `shortcuts list`
	* Prints every shortcut name, one per line. Quote names that contain spaces or emoji.
	* `-f, --folder-name <folder-name|identifier>` — restrict to one folder; pass `none` for shortcuts that live outside any folder
	* `--folders` — list folder names instead of shortcuts
	* `--show-identifiers` — prefix each entry with its stable identifier, which `run` and `view` accept in place of the name
	* Recipes
		* Count them: `shortcuts list | wc -l`
		* Find one: `shortcuts list | grep -i backup`
		* What sits in a folder: `shortcuts list --folder-name 'Shortcutomation'`
		* Which folders exist: `shortcuts list --folders`
* `shortcuts run <name-or-identifier>`
	* Blocks until the shortcut finishes; exit code is non-zero on failure, so `&&` / `||` work
	* `-i, --input-path <file>` — feed a file in as the shortcut’s input
	* `-o, --output-path <file>` — write the shortcut’s output to a file
	* `--output-type <UTI>` — force the result type, e.g. `public.json`, `public.html`
	* Example: `shortcuts run "Shortcutomation - shortcut to html" -i a.json -o a.html`
	* The first call from a given app triggers the one-time Automation permission prompt (System Settings → Privacy & Security → Automation)
* `shortcuts view <name>` — opens that shortcut in the app; the only navigation the CLI offers
* `shortcuts sign --input a.shortcut --output signed.shortcut [--mode anyone|people-who-know-me]` — signs a `.shortcut` file for sharing; `people-who-know-me` is the default mode

## Notes

* Each `shortcuts run` is its own process. A shell loop over 400 shortcuts spawns 400 of them, and every `Run Shortcut` action inside a workflow spawns more again — they linger in Activity Monitor and the run gets progressively slower
* `shortcuts list` reads the local store, so shortcuts created on another device only show up once iCloud sync lands

## References

* <https://sixcolors.com/post/2021/12/run-shortcuts-from-the-mac-command-line>
* <https://support.apple.com/guide/shortcuts-mac/run-shortcuts-from-the-command-line-apd455c82f02/mac>

# iCloud share links

**What do iCloud Shortcut share links actually link to?**

* It’s a link to a point-in-time snapshot at the time you shared it. Any further changes you make will not be reflected in that link.
* It’s permanent, so make a copy and remove the personal information before sharing.
* It presumably gets uploaded to the generic iCloud server that doesn’t belong to anyone’s account, along with some metadata. Although it’s still tied to your account (and that’s why you’re able to stop sharing at any time), no one sees the account info from the shortcut. You can check the metadata by inserting `/api/records/` to the iCloud URL → Change the url part from `icloud.com/shortcuts/<identifier>` to `icloud.com/shortcuts/api/records/<identifier>`, then you could access a dictionary including a download url.

# Constraints & Troubleshooting

* Time limitation: a running shortcut will only stay active for a short period of time (around 3 mins) when you are away from the Shortcuts application
* 如何透過 Siri 呼叫 “Ask for Input” (not just “Dictate Text”) 指令? Add **“Dismiss Siri and Continue”** in the very beginning
