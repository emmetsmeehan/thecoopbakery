# The Coop

Order form for The Coop, served at https://thecoopbakery.com via GitHub Pages.

The menu (items, prices, optional weekly limits) is `menu.json`. The Venmo handle, pickup hours and order cutoff are in the `SETTINGS` block at the top of `index.html`.

## How orders are saved

The form posts each order to a Google Apps Script web app attached to the "The Coop Orders" Google Sheet; its URL is `SETTINGS.sheetUrl` in `index.html`. The script reads `menu.json` from the live site for item names and prices, so a price change is made in one place.

Card and Apple Pay: when `SETTINGS.onlineCheckout` is true, the script opens a Stripe Checkout page for the exact order total and marks the row paid when the customer returns. The Stripe key lives in the script's private Script properties, never in this repository.
