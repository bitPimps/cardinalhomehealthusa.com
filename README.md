# Cardinal Home Health Care Services LLC

Website for [Cardinal Home Health Care Services LLC](https://cardinalhomehealthusa.com) — a St. Louis, MO home health care agency offering in-home care services to seniors and veterans.

## Stack

- Plain HTML, CSS, and vanilla JavaScript
- Single-page application (SPA) with client-side navigation
- Hosted on [GitHub Pages](https://pages.github.com/)

No build step, no dependencies, no framework.

## Project Structure

```
├── index.html          # Single entry point — all pages live here as hidden divs
├── styles.css          # All styles
├── robots.txt          # Search engine directives
├── CNAME               # GitHub Pages custom domain config
├── favicon.ico
├── apple-touch-icon.png
├── docs/
│   ├── CARDINAL-IN-HOME-EMPLOYMENT-APPLICATION.pdf
│   └── CARDINAL-IN-HOME-EMPLOYMENT-APPLICATION.docx
└── images/
    ├── logos/          # Brand logo
    ├── hero/           # Hero section images
    ├── home/           # Home page images
    ├── pages/          # Per-page images (services, careers)
    └── gallery/
        └── 2018/       # 285 Christmas party photos (img001.jpg–img285.jpg)
```

## Pages

The site uses JavaScript-driven tab navigation — all sections are present in the DOM and toggled with the `active` class. There is no routing or URL change on navigation.

| Section | ID | Description |
|---|---|---|
| Home | `#home` | Hero, mission, features, FAQ, CTA |
| Services | `#services` | Four care service descriptions |
| Careers | `#careers` | Job info and application download links |
| Gallery | `#gallery` | 2018 Christmas party photo grid with lightbox |
| Contact | `#contact` | Address, phone, fax, email, hours |

## Services Offered

- **Consumer Directed Services** — client-chosen personal care assistants (family/friends)
- **Personal In-Home Care** — meals, grooming, medication, bathing, and more
- **Private Duty** — private-pay oversight not covered by state funding
- **VetAssist®** — specialized care for U.S. Veterans

## Schema.org Structured Data

Three JSON-LD blocks are embedded in `<head>`:

| Type | Purpose |
|---|---|
| `WebSite` | Site identity; Sitelinks Searchbox eligibility |
| `HomeHealthCareAgency` | Local business — address, phone, hours, service areas, offer catalog |
| `FAQPage` | Rich result eligibility (healthcare sites qualify per Google's August 2023 guidance) |

Validate with the [Google Rich Results Test](https://search.google.com/test/rich-results) or [Schema.org Validator](https://validator.schema.org).

## Local Development

No build step required. Open `index.html` directly in a browser, or serve it locally:

```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

Then visit `http://localhost:8080`.

## Deployment

The site deploys automatically via GitHub Pages on every push to `main`. The custom domain is configured in the `CNAME` file (`cardinalhomehealthusa.com`).

## Updating Content

### Contact information
Edit the Contact section in `index.html` (search for `id="contact"`). If phone, email, or address changes, also update the corresponding values in the `HomeHealthCareAgency` JSON-LD block in `<head>`.

### Services
Edit the Services section (`id="services"`) and update the `hasOfferCatalog` entries in the `HomeHealthCareAgency` JSON-LD block to match.

### FAQ
The FAQ accordion is in the Home section (`id="home"`). Any changes must also be reflected in the `FAQPage` JSON-LD block — Google requires schema content to match what is visible on the page.

### Gallery
Add images to `images/gallery/2018/` following the `imgNNN.jpg` naming pattern and update the `targetCount` variable in the `<script>` block at the bottom of `index.html`.

### Employment application
Replace the files in `docs/` with updated versions, keeping the same filenames so existing links remain valid.

## Contact

**Cardinal Home Health Care Services LLC**
1100 North Sarah Street, St. Louis, MO 63113
Phone: [314-241-4663](tel:+13142414663)
Email: [cardinalhomecare@gmail.com](mailto:cardinalhomecare@gmail.com)
Hours: Daily 10:00 am – 2:00 pm
