# SkinTheory-Website-ST10534064
Web development school project by Zamavezi Kweyama -ST10534064

Static HTML site for **Skin Theory**, a fictional British natural skincare brand (est. 1987) specializing in two product lines: **tissue oils** and **body lotions**.
 
---
 
## 1. Overview
 
| | |
|---|---|
| **Brand** | Skin Theory |
| **Founded** | 1987, London |
| **Categories** | Tissue Oils, Body Lotions |
| **Currency** | ZAR (R) |
| **Pages** | 8 |
| **Styling** | None (plain HTML, no CSS) |
| **Backend** | None (static site, mock cart, GET-based form) |
 
---
 
## 2. Page Structure
 
| # | File | Page Name | Purpose |
|---|---|---|---|
| 1 | `index.html` | Home | Banner, brand intro, 3 featured products |
| 2 | `about.html` | About | Story, mission, vision, philosophy |
| 3 | `products.html` | Products | Full catalogue (16 items) |
| 4 | `giftsets.html` | Gift Sets | 5 curated bundles |
| 5 | `enquiry.html` | Enquiry | Order/contact form |
| 6 | `thankyou.html` | Thank You | Form submission confirmation |
| 7 | `added.html` | Added to Cart | Mock cart confirmation |
| 8 | `contact.html` | Contact | Store locations, email, socials |
 
**Shared elements (every page):**
- Header: `SKIN THEORY` logo linking to `index.html`
- Nav bar: `Home | About | Products | Gift Sets | Enquiry | Contact`
- Footer: `© 2026 Skin Theory. Made in the UK.`
---
 
## 3. Site Map / Navigation Flow
 
```
index.html
 ├── about.html
 ├── products.html ──► added.html ──► enquiry.html ──► thankyou.html ──► index.html
 ├── giftsets.html ──► added.html
 ├── enquiry.html ──► thankyou.html
 └── contact.html
```
 
---
 
## 4. Page Details
 
### 4.1 Home (`index.html`)
- Banner image + tagline
- 3 featured product cards → each links to `products.html`
### 4.2 About (`about.html`)
- Sections: **Our Story**, **Mission**, **Vision**, **Our Philosophy**
- 2 images ("the owner", "main about us")
### 4.3 Products (`products.html`)
 
| Category | # of Items | Price Range | Sizes |
|---|---|---|---|
| Tissue Oils | 9 | R300 – R1,050 | 50ml / 100ml |
| Body Lotions | 7 | R550 – R920 | 300ml |
 
Each product has: image, name, number, price, size, description, and "Add to Cart" link → `added.html`.
 
### 4.4 Gift Sets (`giftsets.html`)
 
| Set | Price | Contents |
|---|---|---|
| Glow Starter Set | R1,200 | Smooth Theory Lotion + Botanical Bliss Oil |
| Luxury Spa Set | R2,500 | Glow lo Lotion + Natura Glow Oil + Cloud Skin Lotion |
| Stretch Mark Care Set | R1,800 | Elastic Glow Lotion + Mother and me Lotion |
| Sensitive Skin Set | R2,100 | Dermacare Sensitive Oil + Cloud Skin Lotion + Skin Renewal Lotion |
| Sweet Treat Set | R1,500 | Strawberry Smooth Oil + Vanilla Cloud Oil + Daily Dew Lotion |
 
### 4.5 Enquiry (`enquiry.html`)
 
| Field | Type | Required |
|---|---|---|
| Full Name | text | Yes |
| Email | email | Yes |
| Phone | text | No |
| Message | textarea | Yes |
 
Form method: `GET` → submits to `thankyou.html`.
 
### 4.6 Thank You (`thankyou.html`)
- Confirmation message + link back to `index.html`.
### 4.7 Added to Cart (`added.html`)
- Static confirmation; explicitly labeled as a **demo cart**.
- Links: `Continue Shopping` (products.html) / `Go to Checkout` (enquiry.html).
### 4.8 Contact (`contact.html`)
 
| Location | Address | Phone | Hours |
|---|---|---|---|
| London (flagship) | 14 Chiltern Street, W1U 77 | +44 20 7946 0821 | Mon–Sat, 10:00–17:00 |
| Cape Town | Shop 12, V&A Waterfront, 8001 | +27 21 418 3392 | Mon–Sun, 9:00–16:00 |
| New York | 121 Spring Street, NY 10012 | +1 212 666 0148 | Mon–Sun, 10:00–17:00 |
 
- Email: `hello@skintheory.co.uk`
- Social (TikTok / Instagram / Facebook): `skinTheory.uk`
---
 
## 5. Images
 
Images load from a local `images/` folder (not included in this upload). Referencing is **inconsistent**:
 
| Style | Example | Used In |
|---|---|---|
| `%20`-encoded spaces | `main%20about%20us.jpg` | `about.html`, `index.html` |
| Literal spaces | `oil dripping.jpg` | `products.html` |
 
**Recommendation:** rename all image files to remove spaces entirely (e.g. `main-about-us.jpg`) rather than relying on encoding — safer across servers/hosts.
 
---
 
## 6. Known Issues
 
| # | Issue | File(s) | Severity |
|---|---|---|---|
| 1 | Inconsistent image path encoding (spaces vs `%20`) | Multiple | Medium |
| 2 | Missing closing `</body>` / `</html>` tags | `thankyou.html` | Low |
| 3 | Form uses `method="get"` — exposes name/email/message in the URL; no real backend | `enquiry.html` | High |
| 4 | "Add to Cart" is non-functional (static link only) — already labeled as demo | `products.html`, `giftsets.html` | Low (by design) |
| 5 | Inconsistent product name capitalization (e.g. "Cloud skin Lotion" vs "Cloud Skin") | `products.html`, `giftsets.html` | Low |
| 6 | UK postcode looks incomplete: `W1U 77` | `contact.html` | Low |
| 7 | No stylesheet — unstyled system-default HTML | All pages | Medium |
 
---
 
## 7. Suggested Next Steps
 
1. Add a stylesheet (`styles.css`) for branding and responsive layout.
2. Normalize all image filenames (no spaces) and update `src` references.
3. Switch the enquiry form to `method="post"` and connect it to a real handler (email service, form API, or CMS).
4. Fix the malformed markup in `thankyou.html`.
5. Decide whether to build a real shopping cart or keep the site enquiry-only.
6. Proofread product copy for consistent capitalization and phrasing.
