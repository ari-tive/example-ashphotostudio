# Product.md — AshPhotoStudio

> **For the coding agent:** This is the single source of truth for the entire website. Everything needed to build it is here. Read this fully before writing any code. When ready, initialize an AstroJS project in this directory and build each page as specified below.

---

## Project Summary

**AshPhotoStudio** is the professional portfolio and business website for photographer **Ash Paul**, based in Mumbai, India. Primary goal: Google-indexed business presence that showcases Ash's work and converts visitors into paying clients via WhatsApp.

---

## Tech Stack

| | |
|---|---|
| **Framework** | AstroJS (latest — always reference `astro-docs` MCP for current APIs) |
| **Styling** | Tailwind CSS or scoped CSS in Astro components |
| **Interactivity** | Vanilla JS / Astro islands (carousel, slider, accordion, lightbox) |
| **Forms** | Client-side only — WhatsApp `wa.me` deep link, no backend needed |
| **Map** | Google Maps embed iframe |
| **Hosting target** | Vercel or Netlify (static export) |
| **SEO** | Meta tags, Open Graph, local business schema for Google indexing |

---

## Design System

### Colors
| Role | Value |
|---|---|
| Page background | `#0a0a0a` |
| Surface / card | `#111111` |
| Elevated surface | `#1a1a1a` |
| Border / divider | `#2a2a2a` |
| Text primary | `#ffffff` |
| Text secondary | `#a0a0a0` |
| Accent | `#e0e0e0` |

> The palette is deliberately muted — **photographs are the visual stars**. Every design decision must keep images as the focal point.

### Typography
- **Display / headings:** Serif display font — *Playfair Display* or *Cormorant Garamond* (Google Fonts)
- **Body / UI text:** Clean sans-serif — *Inter* or *DM Sans*
- **Copy tone:** Warm, friendly, professional — personal not corporate

### Shape & Texture Rules
- **Zero rounded corners** — all edges are sharp 90°: cards, buttons, inputs, image frames, modals
- **Glass panels** — sharp-edged transparent surfaces with `backdrop-filter: blur()`, a thin bright `1px` border on the top and left edge to simulate real glass catching light. NOT the coloured glassmorphism style — think physical glass pane
- **Borders:** Thin `1px` lines in `#2a2a2a` or `#333` to define sections and cards
- **Hover states:** Subtle brightness lift or border brightening — no color pops

### Logo / Favicon
- **File:** `favicon.png` (already exists at project root → copy to `/public/favicon.png` during setup)
- **Header logo:** Favicon icon + text **"AshPhotoStudio"** side by side

---

## Photographer Info

| Field | Value |
|---|---|
| Name | Ash Paul |
| Studio | AshPhotoStudio |
| Location | Churchgate, Mumbai, Maharashtra, India |
| Phone / WhatsApp | +91 9699766852 |
| Email | ashpaul102@email.com |
| Experience | Photography since age 10 · 5 years professional experience |
| Social Media | *(placeholders only — do not ask Ash for these)* |

**Bio (use verbatim, preserve the link):**
> Hi! I'm Ash, a passionate photographer from India. I have developed my photography skills from a young age as I have always been fond of cameras! I have a natural talent when it comes to photography — view some of my works [here](/gallery).

---

## Site Structure

### Universal Header
- Left: Favicon icon + "AshPhotoStudio" text as logo
- Right: Nav links → `Home` · `Gallery` · `Compare` · `Contact Us`
- Dark background, `1px` bottom border, sharp edges throughout

### Universal Footer
- Studio name + short tagline
- Quick nav links
- Contact: phone + email
- Social media placeholder icons
- Copyright: *© 2025 AshPhotoStudio. All rights reserved.*

---

## Pages

---

### Page 1 — Home (`/`)

#### Hero Section
- Full viewport height
- Background: subtle crossfade loop between both images below (or use as a static parallax bg with dark overlay)
  ```
  https://i.pinimg.com/1200x/d9/36/9c/d9369ca02e1853f87be6b7845559b81d.jpg
  https://i.pinimg.com/736x/9a/c9/28/9ac928b223973d40542a98aea605d134.jpg
  ```
- Dark overlay on image so text is readable
- **Headline:** *"Capturing Life's Most Precious Moments"*
- **Subheading:** *"Mumbai's professional photo studio for weddings, families, pets & beyond."*
- **CTA buttons:**
  - Primary: `Book a Session →` → `/contact`
  - Secondary: `View Gallery` → `/gallery`

---

#### About Us Section
> Reference design: `examples/about.png` — large bold heading top-left, two text columns below-left, full-height portrait photo flush to the right edge

- **Heading:** `ABOUT ME` (large, bold, display font)
- **Vertical right-side text label:** `PHOTOGRAPHER — ASH` (rotated 90°, subtle)
- **Left column — "ABOUT ME":**
  > Hi! I'm Ash, a passionate photographer from India. I have developed my photography skills from a young age as I have always been fond of cameras! I have a natural talent when it comes to photography — view some of my works [here](/gallery).
- **Right column — "ABOUT MY WORK":**
  > Every session begins with a conversation. I focus on understanding what you want to feel when you look back at your photos — then I create images that carry that emotion naturally. From golden-hour portraits to candid family chaos, I bring the same careful eye and genuine care to every shoot.
- **Experience stat line:** *"10+ years behind the lens · 5 years professional · Mumbai & beyond"*
- **Portrait photo:** `https://i.pinimg.com/1200x/cb/f9/58/cbf958a59f2950ad7bc211ce50961166.jpg`

---

#### My Works Section (Services)
- Section heading: `MY WORKS`
- Grid of service cards (sharp-edged, glass-panel style)
- **Click to expand** — each card accordion-expands in place to reveal the 2–3 line description below the title
- **Services:**

| Service Title | Expanded Description |
|---|---|
| **Wedding Photography** | Timeless storytelling on your most important day. We blend candid moments with elegantly posed portraits to create a complete visual narrative of your wedding from ceremony to celebration. |
| **Honeymoon Shoots** | Romantic couple portraits in breathtaking settings. Whether it's a beach, mountains, or a city escape — we travel to you and create images that feel as magical as the trip itself. |
| **Baby Shoots** | Gentle, warm sessions celebrating new life. We work entirely at your baby's pace to capture those fleeting early expressions, tiny details, and precious first milestones. |
| **Family Shoots** | Everyone together, in one beautiful frame. Indoor or outdoor, formal or relaxed — we make family portraits feel completely natural and genuinely joyful. |
| **Passport & Formal Photos** | Professional ID, passport, and corporate headshots done right — quick, crisp, and compliant with all standard government and corporate specifications. |
| **Pet Shoots** | Your furry family members deserve great photos too. Fun, playful sessions designed around your pet's energy and personality — no two are ever the same. |
| **Photojournalism** | Real moments, raw and unscripted. Ideal for events, community stories, and editorial assignments that demand authentic visual truth without any staging. |
| **Documentary Photography** | Long-form visual narratives that tell a complete story — for NGOs, businesses, cultural projects, and personal journeys that deserve to be remembered in full. |
| **Architecture & Interior Photography** | Showcasing spaces for hotels, motels, builders, and interior designers. We make rooms, facades, and properties look their absolute best for marketing and portfolios. |

---

#### FAQ Section
- Accordion list — sharp-edged rows, expand/collapse on click
- Section heading: `FREQUENTLY ASKED QUESTIONS`

| Question | Answer |
|---|---|
| How do I book a session? | Simply reach out via our Contact page — fill in the form and it'll open a WhatsApp chat directly with Ash. We'll discuss your vision, pick a date, and get you scheduled. |
| How long does a session typically take? | It depends on the type of shoot. Passport photos take 15–20 minutes. Family and baby shoots run 1–2 hours. Wedding coverage can span a full day. We'll give you a clear timeline when booking. |
| When will I receive my edited photos? | Standard turnaround is 5–7 working days. Rush delivery is available on request. You'll receive a private online gallery link to download your high-resolution images. |
| Do you travel for shoots? | Yes! Ash is based in Churchgate, Mumbai, but regularly travels across Maharashtra and beyond. Destination shoots — honeymoons, destination weddings — are available; inquire for travel pricing. |
| What should I wear or bring? | We'll send you a personalised prep guide after booking. Generally — wear what makes you feel confident, keep outfits simple, and avoid busy patterns that distract from faces. |
| How many photos will I receive? | Edited deliverables vary by package — typically 50–100 for a standard session, 300–500+ for full wedding coverage. All delivered as high-resolution digital files. |
| Do you offer packages or is everything custom priced? | We offer both. Standard packages are listed under our Services. For custom or multi-event requirements, contact us directly for a tailored quote. |
| Can I request specific shots or a style? | Absolutely. Share inspiration images or a mood board when you get in touch — Ash will incorporate your references while bringing his own creative eye to the session. |

---

### Page 2 — Gallery (`/gallery`)

- Stack of full-width infinite carousel rows, one per category
- Alternating scroll direction per row (Row 1: right→left, Row 2: left→right, etc.)
- **Hover** on any row → pauses that carousel
- **Click any image** → opens full-size lightbox modal (sharp-edged overlay, close on Escape or click-outside)
- Fixed carousel row height; images maintain natural aspect ratio within it
- Bold category label above each row

#### Category: WEDDING *(right → left)*
```
https://i.pinimg.com/1200x/41/8d/ec/418decab3e5047d4d8b22588d2402ba7.jpg
https://i.pinimg.com/1200x/91/c6/7a/91c67a2679beb90419bd7004b958a793.jpg
https://i.pinimg.com/736x/17/76/1f/17761f22cc1ebdd044488ed110287502.jpg
https://i.pinimg.com/1200x/a5/44/b8/a544b86495d0ef5c81f479dc14d05517.jpg
https://i.pinimg.com/1200x/39/30/b3/3930b3176d8769a9eb45faa8ad515da7.jpg
https://i.pinimg.com/736x/83/09/0a/83090af8fd46f56839ed84a852f7c9b8.jpg
https://i.pinimg.com/736x/98/9a/20/989a2062f2fa3a18d7d5026fe650e398.jpg
https://i.pinimg.com/736x/03/ab/81/03ab81ee51776259ac31113260e7f639.jpg
https://i.pinimg.com/736x/0d/71/b3/0d71b3adde5e9443005f094bb76b42f2.jpg
https://i.pinimg.com/736x/0e/3c/b7/0e3cb7ef43bd76244fc50109ea05d263.jpg
https://i.pinimg.com/736x/e2/bf/3d/e2bf3d6020b1ff1da5d57d28c6df2e17.jpg
https://i.pinimg.com/736x/81/35/77/81357784b35e1231c9066825f0ccf258.jpg
```

#### Category: HONEYMOON *(left → right)*
```
https://i.pinimg.com/736x/d3/60/9b/d3609b009b9cf68b54e2e29534f26f54.jpg
https://i.pinimg.com/736x/88/8a/f1/888af1c8743f10ca8bd932c512a2c27d.jpg
https://i.pinimg.com/1200x/2d/ed/45/2ded45cdc70c36ae8ddffce2bb246479.jpg
https://i.pinimg.com/736x/96/f9/cc/96f9ccc430ab081c1bca10396f73245f.jpg
https://i.pinimg.com/736x/eb/8f/9b/eb8f9bbf76730c57e2251ab69c9f6ea2.jpg
https://i.pinimg.com/1200x/b1/3c/9d/b13c9dc7ce6a46977e482d3ac751e334.jpg
https://i.pinimg.com/736x/00/4e/79/004e796d42cc4b76b801d53201784a0a.jpg
https://i.pinimg.com/736x/fa/83/12/fa83128509e75680a0611f2924a63f0a.jpg
https://i.pinimg.com/736x/07/c1/15/07c115d5b83da940688b36d02926cfed.jpg
https://i.pinimg.com/736x/6a/be/4d/6abe4d636843b0e1d9d4a54ff4b8232a.jpg
https://i.pinimg.com/736x/78/95/c2/7895c288e2ae82f3345adcd763c5b1b1.jpg
https://i.pinimg.com/736x/87/e9/7a/87e97aa08db3cce21728198c6436a8a9.jpg
https://i.pinimg.com/736x/e8/03/2c/e8032c5042c3935c4338d34e673862fa.jpg
https://i.pinimg.com/736x/16/01/21/1601210956ffeb785f6f393ebf788e47.jpg
https://i.pinimg.com/1200x/05/2c/fd/052cfdc6fb8d5a22a7bd08dd776510b5.jpg
https://i.pinimg.com/1200x/03/24/56/032456b2c772aa03c8f476b94fae9a75.jpg
```

#### Category: PETS *(right → left)*
```
https://i.pinimg.com/1200x/dc/1f/ae/dc1fae59bc01819c582036cfe33e6cf3.jpg
https://i.pinimg.com/736x/d5/3b/59/d53b5959f7371e58e2317f61d7971a61.jpg
https://i.pinimg.com/1200x/84/2e/45/842e451269dc5457a0092e1e49012f9c.jpg
https://i.pinimg.com/1200x/9e/df/9b/9edf9b6c85ec664ea6da30d59993faa5.jpg
https://i.pinimg.com/736x/fb/84/60/fb8460eb432a12f8b2a52155deb2e1cd.jpg
https://i.pinimg.com/1200x/25/74/12/2574128773702926c0c1901d4ad7e7c3.jpg
https://i.pinimg.com/736x/43/5d/a7/435da763975e0c441b51d894acb31a40.jpg
https://i.pinimg.com/736x/6b/8e/30/6b8e306fcf30307013acc7b7104830dc.jpg
https://i.pinimg.com/736x/cd/be/30/cdbe30f23ba6fe2df5c138b2f0defcd9.jpg
https://i.pinimg.com/736x/f5/f7/20/f5f7205402d6f5b42df26815ecb8fa71.jpg
https://i.pinimg.com/736x/7e/d2/74/7ed2745246474b36d834f6b3aa86c8dc.jpg
https://i.pinimg.com/1200x/37/23/bc/3723bce296638efc8c46232c6197ff1f.jpg
https://i.pinimg.com/1200x/97/cc/55/97cc552909cb12aa53f62223d54a81ce.jpg
https://i.pinimg.com/1200x/72/79/8b/72798be457a90a53856bfd5426ee404c.jpg
https://i.pinimg.com/1200x/b5/0b/df/b50bdfbfcaf610540bc85aaff7c33104.jpg
https://i.pinimg.com/1200x/2e/56/d8/2e56d8c2b74392cabdfab7e035a65c41.jpg
https://i.pinimg.com/1200x/a5/ee/d6/a5eed63c5faa224e178e9ebcf53ebb2e.jpg
```

#### Category: ARCHITECTURE & INTERIORS *(left → right)*
```
https://i.pinimg.com/736x/56/9e/45/569e45d158cbc48e4bf4bba74cb20658.jpg
https://i.pinimg.com/736x/b3/a7/e4/b3a7e498f7c9d9db8449be9fd08f3e6d.jpg
https://i.pinimg.com/1200x/8a/0c/9e/8a0c9eeb175892782b9064ec312ec239.jpg
https://i.pinimg.com/736x/bd/b9/2d/bdb92d04250b48e028178add5b2c0c62.jpg
https://i.pinimg.com/736x/d6/3c/27/d63c27f0fd92fa6c7319dbb67a88cd32.jpg
https://i.pinimg.com/1200x/db/bd/e9/dbbde9f3db8f29ec0c79eaf79e6eed26.jpg
https://i.pinimg.com/736x/47/f6/40/47f64097d37329493a7057e9be0229d3.jpg
https://i.pinimg.com/736x/e7/85/f8/e785f878577dd5d05cd455bf773ca5f2.jpg
https://i.pinimg.com/736x/ca/85/9f/ca859f3ed70ec1e3d2b83ac3d8cd80d6.jpg
https://i.pinimg.com/236x/c0/c4/9b/c0c49bfd22514d8601607e5cbacb2e2e.jpg
https://i.pinimg.com/1200x/ac/e3/2b/ace32be8a64cc24f0b276059adfb86b3.jpg
https://i.pinimg.com/736x/48/42/75/484275648acfc54a5a14cfca329b155d.jpg
https://i.pinimg.com/1200x/d5/41/99/d54199753ee3d7f785b628d6f6ec7d44.jpg
https://i.pinimg.com/736x/61/ff/c0/61ffc0dd66757f00f0c53ba5360b3073.jpg
https://i.pinimg.com/1200x/a4/ba/1a/a4ba1a21c13e3d09d3ddb94aeb2ef142.jpg
https://i.pinimg.com/1200x/1e/26/92/1e26921a9d4236c8d6382c2ecd810d18.jpg
https://i.pinimg.com/1200x/38/6f/10/386f108a76a456ea841ef4af36c861cd.jpg
```

---

### Page 3 — Compare (`/compare`)

> Reference design: `examples/compare.png`

**Intro heading + subtext (above the comparisons):**
- Heading: `BEFORE & AFTER`
- Subtext: *"Every photo tells a story — but the edit is where that story comes alive. Ash applies careful colour grading, exposure correction, and retouching to bring out the true mood of every image. Drag the slider to see the transformation."*

**Slider mechanics:**
- Draggable vertical divider bar that follows mouse/touch position across the image
- Left half reveals BEFORE (unedited), right half reveals AFTER (edited)
- `BEFORE` label chip on the left side, `AFTER` label chip on the right side
- Sharp-edged drag handle on the divider line (no rounded pill shapes)
- Works on both desktop (mouse drag) and mobile (touch drag)

**Layout:** 6 full-width comparison pairs stacked vertically with spacing between them

**Image pairs (local files, all in `/images/` folder at project root — copy to `/public/images/` during setup):**

| Pair | Before file | After file |
|---|---|---|
| 1 | `images/b1.png` | `images/a1.png` |
| 2 | `images/b2.png` | `images/a2.png` |
| 3 | `images/b3.png` | `images/a3.png` |
| 4 | `images/b4.png` | `images/a4.png` |
| 5 | `images/b5.png` | `images/a5.png` |
| 6 | `images/b6.png` | `images/a6.png` |

---

### Page 4 — Contact Us (`/contact`)

#### Section 1 — Contact Info, Form & Map

Three-column layout (stack to single column on mobile):

**Column 1 — Contact Details**
- Phone: +91 9699766852
- Email: ashpaul102@email.com
- Address: Churchgate, Mumbai, Maharashtra, India
- WhatsApp button linking to `https://wa.me/919699766852`

**Column 2 — Enquiry Form**
- Fields:
  - Name (text)
  - Email (email)
  - Phone (tel)
  - Service Interested In (dropdown with all 9 services)
  - Message (textarea)
- Submit button label: `Send on WhatsApp →`
- **On submit behavior (client-side only, no backend):**
  Constructs and opens this URL:
  ```
  https://wa.me/919699766852?text=Hi+Ash!+I'm+[Name].+I'm+interested+in+[Service].+[Message]
  ```

**Column 3 — Map**
- Google Maps iframe embed centred on Mumbai:
  `https://www.google.com/maps/place/Mumbai,+Maharashtra/`
- Sharp `1px` border frame around the map

---

#### Section 2 — Reviews (same page, scroll down)

**Heading:** *"Still Thinking Hard? Here's What Our Clients Say!"*

**Layout:** Responsive CSS grid — 3 columns on desktop, 2 on tablet, 1 on mobile. 7–8 cards total. Google-review card style: star rating, reviewer name, avatar initial circle, review body text. Sharp-edged cards with glass panel texture.

**Review cards:**

| Name | Stars | Category | Review text |
|---|---|---|---|
| Priya Mehta | ★★★★★ | Wedding | *"Ash captured our wedding so beautifully — every candid, every tear, every laugh. We look at these photos every anniversary. Truly magical work."* |
| Rohan & Sneha D. | ★★★★★ | Honeymoon | *"We booked Ash for our Goa honeymoon shoot and the results were beyond our expectations. He made us feel completely at ease. The photos look like they're from a magazine!"* |
| Kavita Iyer | ★★★★★ | Baby Shoot | *"My little one is only 3 months old and Ash was so patient and gentle throughout. The photos are absolutely precious — I'm getting them all framed."* |
| The Sharma Family | ★★★★★ | Family Shoot | *"We've been trying to get a good family photo for years — Ash nailed it in the first session. The kids were laughing, everyone looked natural. Highly recommend!"* |
| Arjun Nair | ★★★★★ | Architecture | *"We hired Ash for our new hotel property shots and the photos have been a game changer for our website and marketing material. Incredibly professional."* |
| Meghna Joshi | ★★★★★ | Pet Shoot | *"My golden retriever Bruno has never looked so handsome! Ash has a gift for getting animals to cooperate just long enough. We love every single shot."* |
| Suresh Kapoor | ★★★★★ | Passport Photo | *"Quick, professional, and the photos were perfect on the first try. Best passport photo experience I've ever had — no retakes needed!"* |
| Ananya & Dev | ★★★★★ | Wedding | *"From the pre-wedding shoot to the reception, Ash was everywhere at the right moment. Our families were blown away by the album. Worth every rupee."* |

---

## Assets Reference

| Asset | Location | Status |
|---|---|---|
| Favicon | `favicon.png` (root) → copy to `/public/favicon.png` | ✅ Ready |
| Hero images | Two Pinterest URLs in Home → Hero section | ✅ Ready |
| Ash portrait | `https://i.pinimg.com/1200x/cb/f9/58/cbf958a59f2950ad7bc211ce50961166.jpg` | ✅ Ready |
| Gallery — Wedding (12 images) | URLs listed above | ✅ Ready |
| Gallery — Honeymoon (16 images) | URLs listed above | ✅ Ready |
| Gallery — Pets (17 images) | URLs listed above | ✅ Ready |
| Gallery — Architecture (17 images) | URLs listed above | ✅ Ready |
| Compare pairs (×6) | `images/b1–b6.png` & `images/a1–a6.png` → copy to `/public/images/` | ✅ Ready |
| Social media handles | Footer | 🔇 Placeholder only — do not ask |
