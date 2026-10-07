# The Coop

Order form for The Coop, served at https://thecoopbakery.com via GitHub Pages.

Menu, prices, Venmo handle and pickup hours are in the `SETTINGS` and `MENU` blocks at the top of `index.html`.

## How orders are saved

The form posts each order to a Google Apps Script web app attached to the "The Coop Orders" Google Sheet; its URL is `SETTINGS.sheetUrl` in `index.html`.

Per-item weekly limits (`limit` in `MENU`) are off. Before turning them on, update the script's `doGet` to compare pickup dates in the spreadsheet's time zone (`getSpreadsheetTimeZone()`), then deploy a new version.
