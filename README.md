# products.comfortvision.com

Public product info site. Static only — no Firebase, no auth, no links to any other CV/Optik app. Keep it that way.

Files
- index.html — public page. `#product-id` in the URL opens that product; no hash shows the catalog.
- products.json — all product content. Add a product = add an entry here.
- qr.html — staff QR generator. Not linked anywhere; share the URL internally only.
- netlify.toml — security headers. robots.txt blocks indexing.

Adding a product
Copy an existing entry in products.json. Fields:
- id: lowercase-with-dashes, used in the URL and QR code. Don't change it after printing codes.
- category: "lenses" or "frames"
- heroColor / heroText: hex colors for the top banner
- features: up to 3, icon is one of bolt, sun, palette, shield, feather, sparkles, eye
- options: colors or finishes (name, hex, tagline, bullets)
- details: "Good to know" bullets

Deploy
Separate Netlify site from the patient-db site. Custom domain products.comfortvision.com → add in Netlify > Domain management, then a CNAME on comfortvision.com pointing `products` to the Netlify site.
