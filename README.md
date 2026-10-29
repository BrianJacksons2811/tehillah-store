# TEHILLAH storefront

## Updated multipage edition

Open `index.html` for Home. The navigation links to `shop.html`, `edit.html`, `about.html` and `contact.html`. Products open on `product.html?id=p1` (or another configured product ID); `size-guide.html` explains sizing. All pages share the saved bag. Upload every HTML file together with the shared CSS, JavaScript and assets.

The header is sticky at the top while scrolling. Backgrounds use warm stone/ivory rather than pure white. Motion respects reduced-motion preferences.

Product pages let shoppers choose UK, EU, US Men or US Women labels. Sample variants are stored canonically as UK sizes; selected system and canonical size appear in the bag and outgoing requests. The illustrative adult conversion table lives in `app.js` (`sizeMap`) and `size-guide.html`. Replace BOTH with supplier-approved conversions before live trading. Changing display systems does not create separate inventory.

Verification: all seven pages passed script-initialization checks using a simulated DOM; sizing-system changes, persisted bag labels, invalid-product handling and local page/asset links were checked. JavaScript syntax checks passed. Browser inspection was blocked by the preview browser's access policy, so responsive appearance and sticky behavior still need visual verification in your browser.

A custom HTML, CSS and JavaScript storefront. No WordPress, WooCommerce, framework, installation or build step. Open this folder in VS Code and open `index.html` in a modern browser; VS Code Live Server is also suitable. Fonts load from Google Fonts, with local fallbacks when offline.

## Edit the store

- `index.html`: page sections and text.
- `styles.css`: layout, colours, typography and responsive design.
- `config.js`: products, sample prices, sizes, availability, business email and WhatsApp number.
- `app.js`: filters, product details, shopping bag and order-message preparation.
- `assets/moodboard.png`: rendered page 2 of the supplied TEHILLAH moodboard. Images are displayed using CSS crops for the concept. They are reference imagery, not proof of actual stock. Replace them with approved individual product photos before launch.

The design follows the supplied identity: Botswana, footwear first, black/ivory/cobalt, Manrope/Inter, a text TEHILLAH wordmark and provisional T. mark. The reference shops inspired collection storytelling and shopping navigation. No competitor assets are included.

## What works now

Product search and category filters; product dialogs and size selection; bag quantities, removal, subtotals and persistence on the same browser; responsive page styling; order form validation; WhatsApp/email message preparation when configured. The bag contains only product IDs, sizes and quantities in localStorage. Contact form details are not stored.

## Enable ordering

1. Replace every sample product, price, size, stock value, image and description with approved catalogue information. Confirm the size system. Remove unused sample categories.
2. Enter the WhatsApp number in `config.js`, using country code and digits only (no +, spaces or punctuation). Enter the business email.
3. Publish approved delivery and return terms using `deliveryText`; add complete business/policy information as required for launch.
4. Set `ordersEnabled: true` only when ready.
5. Send a test order through BOTH channels from a phone and a desktop. Confirm that the correct business receives the complete item list, variants, quantities, subtotal and customer details.

WhatsApp opens a prefilled conversation. Email opens the visitor's email app using `mailto:`. The visitor must press Send. Some visitors have no email app configured, and very large messages may exceed app limits. Neither channel automatically sends messages, confirms receipt, reserves stock, creates an order record, accepts payment or clears the bag. The business must confirm stock, delivery cost, final price and payment instructions. Browser-calculated prices are requests only and must be checked by the business.

## Hosting

Upload the folder contents (including `assets/`) to your hosting account's public web directory, commonly `public_html`. Serve using HTTPS. This static version needs no Node.js process, PHP or database. A shared hosting package that serves static HTML/CSS/JS can host it; package choice depends on storage, email and support needs, rather than an application server. Keep a local backup before replacing hosted files.

For individual product photos, add an image path to each product and adapt `.shoe-image`/the rendering functions to use that path. The current image variants intentionally reuse the moodboard reference and are prominently labelled as samples.

## Deliberately deferred

No real customer accounts/profiles, automatic email sending, payment collection, live inventory, staff admin or durable order history. These need a trusted backend or external service. Do not put passwords or email-service secrets into these JavaScript files. A small PHP email endpoint could be added later on compatible shared hosting, with server validation, spam/rate protection and authenticated mail delivery. Real profiles require secure server-side authentication and storage.

## Before public launch

Replace moodboard/reference assets with approved photos; verify contact details and policies; test actual message delivery and mobile layouts; review image rights; remove sample notices only after all sample data is replaced. Google Fonts receives font requests; self-host the font files if you want to remove that external dependency. No analytics or marketing trackers are included.
