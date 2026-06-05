# Shopamp – Clothing Store Landing Page

A fully responsive, semantic HTML5 & CSS3 landing page for a clothing store. No frameworks, no dependencies — just clean vanilla HTML and CSS.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [File Structure](#file-structure)
3. [Getting Started](#getting-started)
4. [Page Sections](#page-sections)
5. [Design System](#design-system)
6. [CSS Architecture](#css-architecture)
7. [Responsiveness](#responsiveness)
8. [Semantic HTML Structure](#semantic-html-structure)
9. [Customization Guide](#customization-guide)
10. [Typography](#typography)
11. [Images](#images)
12. [Accessibility](#accessibility)
13. [Browser Support](#browser-support)

---

## Project Overview

**Shopamp** is a single-page clothing store website template built with:

- Pure **HTML5** with semantic tags
- **CSS3** with custom properties (CSS variables)
- **Google Fonts** (Cormorant Garamond + DM Sans)
- No JavaScript frameworks or CSS libraries required
- Fully **mobile-responsive** via CSS media queries

### Features at a Glance

| Feature | Detail |
|---|---|
| Sections | 12 fully styled sections |
| Responsive | Mobile, tablet, desktop |
| Dependencies | Google Fonts only |
| Framework | None (Vanilla HTML/CSS) |
| Semantic Tags | `header`, `nav`, `main`, `section`, `article`, `footer`, `address`, `blockquote` |
| Animations | CSS keyframes + hover transitions |

---

## File Structure

```
shopamp/
│
└── index.html       # Complete single-file landing page (HTML + CSS)
```

All CSS is embedded in a `<style>` block inside `<head>`. The page is fully self-contained in one file.

---

## Getting Started

### 1. Clone or Download

Download `index.html` and open it directly in any modern browser — no build step required.

```bash
# If using a local server (recommended)
npx serve .
# or
python -m http.server 8000
```

### 2. Open in Browser

```
http://localhost:8000/index.html
```

Or simply double-click `index.html` to open it directly.

---

## Page Sections

The page is divided into **12 sections** from top to bottom:

### 1. Header / Navigation
- Sticky header that stays at top on scroll
- Frosted-glass effect (`backdrop-filter: blur`)
- Logo on the left, nav links + CTA button on the right
- Hides nav links on mobile (hamburger menu not included — extend as needed)

```html
<header>
  <nav> ... </nav>
</header>
```

---

### 2. Hero Banner
- Full-width image with dark overlay (`filter: brightness`)
- Large display heading and subtitle text overlaid bottom-left
- Fade-up CSS animation on page load (`@keyframes fadeUp`)

```html
<section class="hero" aria-label="Hero banner">
  <img class="hero-img" src="..." alt="..." />
  <div class="hero-content">
    <h1>Clothing<br>Store</h1>
    <p>Clothing Website Template</p>
  </div>
</section>
```

---

### 3. About Us
- Three-column card grid
- Each card: image thumbnail, category label, title, description, and "Learn more" link
- Uses `<article>` tags for semantic meaning
- Images zoom gently on hover

```html
<section id="about">
  <div class="section-inner">
    <h2 class="section-title">About Us</h2>
    <div class="cards-grid">
      <article class="card"> ... </article>
      ...
    </div>
  </div>
</section>
```

---

### 4. Sale Banner
- Full-width background image with dark overlay
- Centered headline and CTA button
- Links to the `#products` section

```html
<section class="sale-banner" aria-label="Sale announcement">
  <img class="sale-banner-img" ... />
  <div class="sale-content">
    <h2 class="sale-title">Sale to −70% Last 2 Days</h2>
    <a href="#products" class="btn btn-primary">Watch Now</a>
  </div>
</section>
```

---

### 5. Features
- Two-column layout: heading on the left, 2×2 feature grid on the right
- Each feature has an inline SVG icon, name, and short description
- Four features: Sale, Delivery, Our Clients, Warranty
- Uses a light grey background (`--light-bg`)

```html
<section id="features">
  <div class="features-layout">
    <div class="features-heading"> ... </div>
    <div class="features-grid">
      <div class="feature-item"> ... </div>
      ...
    </div>
  </div>
</section>
```

---

### 6. Our Products
- 2×2 product image grid (max 720px wide, centered)
- Each product card: image with zoom-hover, product name, price
- Product names styled in uppercase blue

```html
<section id="products">
  <div class="section-inner">
    <h2 class="section-title">Our products</h2>
    <div class="products-grid">
      <article class="product-card"> ... </article>
      ...
    </div>
  </div>
</section>
```

---

### 7. Newsletter
- Centered layout on light background
- Headline, subtitle, referral hint text
- Inline email input + subscribe button form

```html
<section id="newsletter">
  <div class="newsletter-inner">
    <h2>Be the first to know?</h2>
    <form class="newsletter-form">
      <input type="email" placeholder="Enter your email here …" />
      <button type="submit">Subscribe</button>
    </form>
  </div>
</section>
```

---

### 8. Shop Mosaic
- Asymmetric image mosaic: 1 tall image left + 2 stacked images right
- Overlay label and "BUY NOW" text on each image
- Hover zoom on all images

```html
<section id="shop">
  <div class="shop-inner">
    <div class="shop-mosaic">
      <div class="shop-item item-large"> ... </div>
      <div>
        <div class="shop-item"> ... </div>
        <div class="shop-item"> ... </div>
      </div>
    </div>
  </div>
</section>
```

---

### 9. Latest News
- Three-column news card grid
- Each card: image, article title, "Learn More" link
- Cards have white background on a grey section background

```html
<section id="news">
  <div class="section-inner">
    <h2 class="section-title">Latest News</h2>
    <div class="news-grid">
      <article class="news-card"> ... </article>
      ...
    </div>
  </div>
</section>
```

---

### 10. Last Collection
- Inline header with title + "Learn More" link side by side
- 3×2 photo gallery grid
- All images zoom on hover

```html
<section id="collection">
  <div class="collection-header">
    <h2>Last Collection</h2>
    <a href="#">Learn More</a>
  </div>
  <div class="collection-gallery"> ... </div>
</section>
```

---

### 11. Testimonials
- Centered layout on light background
- Circular avatar image with blue border
- Customer name, role, and `<blockquote>` testimonial text in italic serif font
- Previous / Next navigation buttons (styled circles)

```html
<section id="testimonials">
  <div class="testimonial-inner">
    <div class="testimonial-avatar"> <img ... /> </div>
    <p class="testimonial-name">Markus Grecho</p>
    <blockquote class="testimonial-text"> ... </blockquote>
    <nav class="testimonial-nav">
      <button class="testimonial-btn">‹</button>
      <button class="testimonial-btn">›</button>
    </nav>
  </div>
</section>
```

---

### 12. Our Location
- Email + Phone contact block using `<address>` tag
- Side-by-side layout: store photo + embedded Google Map `<iframe>`

```html
<section id="location">
  <div class="location-inner">
    <address class="contact-item"> ... </address>
    <div class="location-grid">
      <img ... />
      <div class="map-placeholder">
        <iframe src="https://maps.google.com/..." title="Store location on map"></iframe>
      </div>
    </div>
  </div>
</section>
```

---

### 13. Footer
- Three-column layout: brand blurb + social links | News links | Shop links
- Logo repeated in footer
- Social links as circular icon buttons
- Copyright bar at bottom

```html
<footer>
  <div class="footer-inner">
    <div class="footer-grid">
      <div> <!-- Brand + social --> </div>
      <div class="footer-col"> <!-- News links --> </div>
      <div class="footer-col"> <!-- Shop links --> </div>
    </div>
    <p class="footer-bottom">© Copyright ...</p>
  </div>
</footer>
```

---

## Design System

All design tokens are defined as **CSS custom properties** in `:root`:

```css
:root {
  --blue:      #1a6eff;   /* Primary brand color */
  --blue-dark: #0d55d4;   /* Hover state for blue */
  --text:      #1c1c1c;   /* Primary body text */
  --muted:     #6b7280;   /* Secondary/caption text */
  --light-bg:  #f4f5f7;   /* Alternate section background */
  --white:     #ffffff;   /* Base background */
  --border:    #e5e7eb;   /* Dividers and input borders */

  --font-display: 'Cormorant Garamond', Georgia, serif;
  --font-body:    'DM Sans', sans-serif;
}
```

To retheme the entire site, only these variables need to change.

---

## CSS Architecture

### Button System

Two button variants share the `.btn` base class:

```css
/* Base */
.btn { padding: 0.55rem 1.4rem; border-radius: 50px; font-size: 0.82rem; }

/* Filled */
.btn-primary { background: var(--blue); color: white; }

/* Outlined */
.btn-outline { border: 2px solid var(--blue); color: var(--blue); }
```

Usage:
```html
<a href="#" class="btn btn-primary">Buy Now</a>
<a href="#" class="btn btn-outline">Learn More</a>
```

### Section Layout Pattern

Most content sections follow this pattern:

```html
<section id="section-name">
  <div class="section-inner">       <!-- max-width: 1100px, centered -->
    <h2 class="section-title">...</h2>
    <!-- content grid -->
  </div>
</section>
```

### Image Hover Zoom Pattern

Used on cards, product images, gallery items, and news cards:

```css
.card-img { overflow: hidden; }
.card-img img { transition: transform 0.5s ease; }
.card-img:hover img { transform: scale(1.04); }
```

### Hero Animation

```css
.hero-content { animation: fadeUp 0.9s ease both; }

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

---

## Responsiveness

Three breakpoints handle all screen sizes:

| Breakpoint | Target | Changes |
|---|---|---|
| `max-width: 900px` | Tablet | 3-col grids → 2-col, footer → 2-col |
| `max-width: 640px` | Mobile | All grids → 1-col, nav links hidden |

```css
@media (max-width: 900px) {
  .cards-grid,
  .features-layout,
  .news-grid,
  .collection-gallery { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 640px) {
  .cards-grid,
  .products-grid,
  .news-grid,
  .collection-gallery,
  .shop-mosaic,
  .location-grid,
  .footer-grid { grid-template-columns: 1fr; }

  .nav-links { display: none; } /* Add a hamburger menu here to extend */
}
```

---

## Semantic HTML Structure

The document uses proper HTML5 semantic elements throughout:

| Element | Used For |
|---|---|
| `<header>` | Site navigation bar |
| `<nav>` | Navigation links (inside header and footer social) |
| `<main>` | All page content sections |
| `<section>` | Each major page section with `aria-labelledby` |
| `<article>` | Individual cards (About Us, Products, News) |
| `<footer>` | Site footer |
| `<address>` | Contact info (email + phone) |
| `<blockquote>` | Testimonial quote |
| `<figure>` | (Extend for captioned images) |
| `aria-label` | Sections without visible headings (hero, sale banner) |
| `aria-labelledby` | Sections with visible `<h2>` headings |

---

## Customization Guide

### Change Brand Color

Find and replace `--blue: #1a6eff` in `:root` with your color:

```css
:root {
  --blue:      #e44d26;  /* e.g. orange */
  --blue-dark: #c73d1a;
}
```

### Change Logo Text

```html
<a href="#" class="logo">YourBrand!</a>
```

### Add a Product Card

```html
<article class="product-card">
  <div class="product-card-img">
    <img src="your-image.jpg" alt="Product description" />
  </div>
  <p class="product-name">Product Name</p>
  <p class="product-price">$ 99.99</p>
</article>
```

### Add a Nav Link

```html
<ul class="nav-links">
  <li><a href="#about">About</a></li>
  <li><a href="#products">Shop</a></li>
  <!-- Add more here -->
  <li><a href="#" class="btn btn-primary">Buy Now</a></li>
</ul>
```

### Replace Hero Image

```html
<img
  class="hero-img"
  src="YOUR-IMAGE-URL.jpg"
  alt="Descriptive alt text"
/>
```

### Update Contact Info

```html
<address class="contact-item" style="font-style:normal;">
  <strong>Email</strong>
  <a href="mailto:your@email.com">your@email.com</a>
</address>

<address class="contact-item" style="font-style:normal;">
  <strong>Phone</strong>
  <a href="tel:+1234567890">+1 234 567 890</a>
</address>
```

### Update Google Maps Embed

Replace the `src` in the map `<iframe>`:

1. Go to [Google Maps](https://maps.google.com)
2. Search for your address
3. Click **Share → Embed a map**
4. Copy the `src` URL and paste it:

```html
<iframe src="YOUR-GOOGLE-MAPS-EMBED-URL" title="Store location on map"></iframe>
```

---

## Typography

| Role | Font | Weight | Usage |
|---|---|---|---|
| Display / Headings | Cormorant Garamond | 300, 400, 600 | `h1`, `h2`, blockquote, logo |
| Body / UI | DM Sans | 300, 400, 500 | All body text, nav, buttons |

Fonts are loaded from Google Fonts:

```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
```

Font size scale uses `clamp()` for fluid typography on headings:

```css
font-size: clamp(3rem, 6vw, 5rem);   /* Hero h1 */
font-size: clamp(2rem, 4vw, 3rem);   /* Section titles */
font-size: clamp(1.8rem, 3.5vw, 2.6rem); /* Sub-headings */
```

---

## Images

All images are currently sourced from [Unsplash](https://unsplash.com) via URL. To use local images:

1. Place your image files in an `images/` folder next to `index.html`
2. Replace the `src` attribute:

```html
<!-- Before -->
<img src="https://images.unsplash.com/photo-xxx?w=600" alt="..." />

<!-- After -->
<img src="images/your-photo.jpg" alt="..." />
```

**Recommended image dimensions:**

| Section | Recommended Size |
|---|---|
| Hero | 1400 × 600 px |
| About / News cards | 600 × 400 px |
| Products | 500 × 520 px |
| Sale banner | 1400 × 500 px |
| Gallery | 500 × 500 px |
| Location store photo | 700 × 320 px |

---
## Video Explanation
https://youtu.be/0iCnU9gK7Sk
