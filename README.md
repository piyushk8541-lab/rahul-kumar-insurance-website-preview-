# Rahul Kumar — Insurance Advisor · Preview Website

A single-file, fully responsive pitch demo for **Rahul Kumar**, authorised partner of **TATA AIG General Insurance** (Patna · Muzaffarpur · Gaya · Chhapra).

**Deliverable:** [`index.html`](index.html) — one self-contained file (inline CSS + vanilla JS). No build step, no dependencies. Open it directly in a browser or host it on any static host (Netlify, Vercel, GitHub Pages, cPanel).

---

## 1. What's inside

| Section | Highlights |
|---|---|
| Sticky navbar | Blur-on-scroll glass header, scroll-spy active link, mobile slide-down menu, yellow CTA |
| Hero | Navy gradient + grid overlay, yellow highlight on "Insurance", advisor photo placeholder on animated yellow blob, 3 floating glass cards (family-protection illustration, claim support, 4.9★ rating) |
| Stats strip | Animated counters (12,500+ clients, 4,800+ claims, 15+ years, 25+ cities) |
| Insurance for Every Journey | Truck / Bus / Car / Bike cards + Health, Life, Home, Travel, Commercial grid |
| Benefits | 5 icon cards with hover lift and gradient underline |
| How It Works | 4-step dotted timeline |
| Why Us + Reviews | Trust reasons + 3-slide testimonial carousel (autoplay, swipe, dots, keyboard) |
| Offices | 4 cards with SVG map, pin, timings, tap-to-call + directions |
| Lead form | Validation, inline errors, sending state, success screen with generated reference no. |
| FAQ | 5-question accordion + WhatsApp help card |
| Footer | Quick links, insurance links, contact, socials, IRDAI disclaimer, agency ribbon |
| Floating | WhatsApp FAB (`wa.me/919835849947`) + mobile sticky Call/WhatsApp bar |

Also included: SEO meta, Open Graph/Twitter tags, `InsuranceAgency` + `LocalBusiness` + `FAQPage` JSON-LD, skip link, ARIA labels, WCAG-AA contrast, `prefers-reduced-motion` support.

---

## 2. Customisation notes — where to change what

### Logo / brand badge
Search for `brand-badge`. It appears **twice** (header + footer). Replace the inline `<svg>` inside the `<span class="brand-badge">` with your own logo:
```html
<span class="brand-badge"><img src="tata-aig-logo.png" alt="TATA AIG" width="48" height="48"></span>
```
The favicon is the `data:image/svg+xml…` link in `<head>` — swap it for `favicon.ico`.

### Advisor photo
Search for `PHOTO PLACEHOLDER` (in the hero). Delete the whole `.advisor-photo` block and drop in a real portrait (use a ~4:4.7 crop, 800×940px):
```html
<img src="rahul-kumar.jpg" alt="Rahul Kumar, TATA AIG authorised insurance advisor, Patna" 
     style="width:100%;height:100%;object-fit:cover" loading="lazy">
```

### Colours
All colours live in one block: `:root{ … }` in the CSS — `--navy`, `--royal`, `--yellow`, `--teal`, `--mist`. Change those six and the entire site re-themes. Fonts: `--font-head`, `--font-body`, `--font-script`.

### Phone & WhatsApp
Find-and-replace all:
- `+91 98358 49947` → display number
- `tel:+919835849947` → click-to-call links
- `wa.me/919835849947` → WhatsApp links (also inside the FAB and mobile bar)

### Email, addresses, timings
Search `rahultatabihar@gmail.com` (header, form help, footer) and the four office blocks under `id="offices"`. Each has one line of address + timings — replace text, and update the Google Maps `href`.

### Numbers in the stats strip
Each counter is `<span class="counter" data-count="12500" data-suffix="+">`. Change `data-count` / `data-suffix` — the animation updates automatically.

### Testimonials
Three `<blockquote class="tst-card">` blocks inside `#tstTrack`. Replace name, city, quote and the initials in `<span class="tst-avatar">`. Add or remove slides and also add/remove a matching `.tst-dot` button.

### Lead form
Options are plain `<option>` tags in `#fType` and `#fCity` — edit freely. Validation lives in the `validators` array in the script (name, 10-digit Indian mobile starting 6–9, type, city, consent). The form currently shows a success state locally — connect a backend by adding `fetch('/api/lead', {method:'POST', body:new FormData(form)})` inside the submit handler (look for `[demo] Lead captured`).

### SEO / schema
Replace `https://www.example.com/` (canonical, OG tags, JSON-LD `@id`s) with the live domain, and add a real `og-image.jpg` (1200×630) to the site root.

### Footer ribbon
Search `Preview Design by` and replace **Pixelbharat Studio** with your agency name.

### Regulator details
The footer shows `TATA-AIG-XXXXXX` as a placeholder partner code — replace it with the real IRDAI registration/agent code before going live.

---

*Disclaimer: preview/demo build. Insurance is the subject matter of solicitation.*
