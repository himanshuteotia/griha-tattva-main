# Griha Tattva — Curated Home Décor

A single-file, self-contained storefront for **Griha Tattva**, a curated home-décor brand rooted in India's craft traditions. The whole site — markup, styles, fonts, and product imagery — is bundled into one HTML file that runs anywhere with no build step.

🔗 **Live:** https://griha-tattva-2.vercel.app

---

## Highlights

- **Self-contained** — all images and fonts are embedded (base64) in `index.html`; no external asset requests, no build step.
- **Cart + WhatsApp checkout** — add to cart, adjust quantities, and place the order via a pre-filled WhatsApp message (no backend required).
- **Image lightbox** — click any product photo for a full-screen, swipeable gallery.
- **Editorial content** — brand story, a Journal with reader overlay, and a Care guide.
- **Animated "journey" timeline** — Clay → Wheel → Glaze → Kiln → Home draws in as you scroll.
- **Modern motion** — staggered hero entrance, scroll-reveal sections, a scroll-progress bar, 3D card tilt, and a magnetic CTA — all respecting `prefers-reduced-motion`.
- **Functional contact form** — submits to Formspree.
- **Fully responsive** — tuned for phones (centered hero, single-column cards, horizontal-scroll filters, sticky cart icon).

## Collections

`Griha Mrida` (Ceramics) · `Griha Pallav` (Nature & Planters) · `Griha Shobha` (Living Décor) · `Griha Vastra` (Soft Furnishings) · `Griha Jyoti` (Ambience) · `Griha Uphaar` (Gifting) · `Griha Vidhu` (Premium)

## Project structure

```
.
├── index.html                      # The deployed site (self-contained bundle)
├── Griha Tattva (Standalone).html  # Working source — edit this, then sync to index.html
├── logo/                           # Brand logo (also embedded in the bundle)
├── product-images/                 # Product photography (also embedded in the bundle)
├── .vercelignore                   # Keeps the deploy to just index.html
└── .claude/launch.json             # Local static-server config for previewing
```

> **Note:** `index.html` is a copy of `Griha Tattva (Standalone).html`. After editing the source, re-sync before deploying:
> ```bash
> cp "Griha Tattva (Standalone).html" index.html
> ```

## Develop locally

Serve the folder with any static server and open `index.html`:

```bash
python3 -m http.server 8123
# then visit http://localhost:8123/
```

## Deploy

Deployed on **Vercel** (static). To ship an update:

```bash
cp "Griha Tattva (Standalone).html" index.html   # sync the deploy copy
vercel --prod                                     # deploy
```

## Configuration

A couple of values live near the top of the embedded scripts in the HTML:

- **WhatsApp order number** — `ORDER_WHATSAPP` (digits only, with country code).
- **Contact form endpoint** — the Formspree URL in the contact handler.

> First contact-form submission from a new domain may require confirming the domain in your Formspree dashboard.

## Roadmap

- Replace placeholder product names/prices with the real catalog.
- Optional: connect this repo to Vercel for auto-deploy on `git push`.
