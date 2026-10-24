# Zephyr — Product Context

## 1. Project Overview

**Zephyr is a responsive, multi-page drone e-commerce prototype** created by a two-person development team for a consulting-firm client as part of a 4Geeks Academy project.

The project takes DJI's existing drone shopping experience as a **reference for product categories, page structure, and shopping journeys**, then proposes a clearer, more modern, easier-to-navigate refresh under the **Zephyr** name. The goal is not to clone DJI's website or imply an official affiliation; it is to demonstrate thoughtful improvements in information hierarchy, discoverability, product comparison, responsiveness, and checkout clarity.

**Technology restriction from the beginning: build with semantic HTML and Tailwind CSS only.** No React, Vue, Angular, Bootstrap, JavaScript-driven UI, back-end services, payment integrations, or other advanced technologies. Git and GitHub are used for collaboration and version control, not as application technologies. Schema.org JSON-LD is permissible as *non-executable structured metadata*.

The deliverable is a **visual and navigable prototype**, not a production e-commerce platform. Every required view must exist as an individual HTML file, link correctly to the others, and demonstrate the intended user journey without pretending that static pages provide real shopping or payment functionality.

---

## 2. Primary Goals

- Present Zephyr as a polished and trustworthy drone storefront.
- Improve on the reference site's usability through clear navigation, readable information, and well-organized product cards.
- Help visitors discover drones, browse by relevant attributes, and understand product capabilities.
- Demonstrate an understandable journey from the home page to catalog, product details, cart, and checkout.
- Deliver a consistent experience on mobile, tablet, laptop, and desktop.
- Use semantic HTML, inclusive accessibility practices, and SEO-friendly, indexable content.
- Include accurate Schema.org structured data when appropriate.
- Achieve **at least 80** in Google PageSpeed Insights on the deployed public URL; **90+ is the preferred target**.
- Demonstrate sound collaboration through feature branches, frequent commits, and reviewed pull requests.

### Target audience

- First-time drone buyers who need product specifications explained clearly.
- Hobbyists and travelers looking for compact camera drones.
- Content creators comparing image quality, portability, and flight features.
- More experienced customers browsing drones and accessories.

These audience groups inform the prototype's content and design; no user account system or personalization engine is required.

---

## 3. Scope and Required Deliverables

At minimum, provide these five linked HTML pages:

| View | File | Purpose |
| --- | --- | --- |
| Home | `index.html` | Introduce Zephyr, feature campaigns, new arrivals, and best sellers. |
| Catalog | `catalog.html` | Display and visually organize a reference set of 20 products. |
| Product details | `product.html` | Show one drone or accessory with essential purchasing information. |
| Cart | `cart.html` | Display three sample items and a purchase summary. |
| Checkout | `checkout.html` | Present a three-step checkout flow as a visual prototype. |

Include `product_context.md`, the existing separate style guide, a shared Tailwind stylesheet or Tailwind setup appropriate to the team's environment, and locally stored assets when practical.

Suggested repository organization (adapt to the existing repo rather than creating duplicate files):

```text
/
├── index.html
├── catalog.html
├── product.html
├── cart.html
├── checkout.html
├── product_context.md
├── assets/
│   └── images/
└── ... shared Tailwind source/output and existing style guide
```

**All navigation must work with ordinary relative HTML links.** The five HTML files must be reachable from each other through appropriate navigation links or calls to action. Avoid dead-end pages.

### Product data ownership (separate source of truth)

**This document defines requirements, layout, behavior, and quality standards only. It must not contain product data.** The team maintains all product records in a separate, existing data file. Contributors and AI assistants must find and read that file before populating product-related content in any HTML page.

- Do not add product names, models, prices, descriptions, technical specifications, product images/paths, inventory status, or fabricated sample records to `product_context.md`.
- Do not create a competing dataset, duplicate the separate data file, or silently replace missing entries with invented values.
- Use product information from the separate file consistently across home cards, catalog cards, product details, cart examples, and any product-related Schema.org markup.
- The assignment’s **20 catalog cards** and **three cart line items** are layout requirements, not data definitions. Populate them from the separate file when sufficient records are available; otherwise flag the gap to the team without fabricating product content.
- If data-file location, field names, or values are unclear, inspect the repository and existing team documentation. Treat the separate file as authoritative and leave it unchanged unless explicitly asked to modify it.

### Shared page elements

The header/navigation and footer must look and behave consistently on **every** view. Because this is an HTML-only prototype, shared components can be repeated as consistent HTML markup across files; do not introduce a templating engine, React components, or JavaScript solely to implement reuse. Keep the repeated markup synchronized during code review.

---

## 4. Design Direction and Content Strategy

Use DJI's current public storefront as **inspiration**, not as code to copy. Retain the familiar expectations of a premium technology shop while making meaningful improvements:

- Stronger visual hierarchy: product purpose, benefits, price, and next action should be easy to scan.
- Simpler category navigation and prominent search affordance.
- Cleaner product cards with consistent specifications and calls to action.
- Clearer explanations of who a drone is for and common use cases.
- More readable shopping summaries and checkout steps.
- Responsive layouts that prioritize essential content on narrow screens.
- Trustworthy presentation without fabricated customer reviews, stock notices, discounts, or technical claims.

**Do not reproduce DJI logos, branded copy, or proprietary imagery without permission.** Zephyr must have its own identity. All product names, categories, descriptions, specifications, images, identifiers, prices, and availability must come from the team’s separate product-data file. Do not derive product records from DJI or invent missing values. Use DJI only as a reference for visual layout and user experience; do not imply Zephyr is affiliated with DJI.

### Style guide ownership

**Do not define or duplicate colors, typography, font choices, or theme tokens in this file.** Those decisions already live in the team's separate style guide. Implement the existing style guide consistently across all pages.

---

## 5. Required View: Home (`index.html`)

### Header / navigation

- Zephyr logo/brand mark, linking to `index.html`.
- Visible product search field or search affordance.
- User account menu/link affordance.
- Accessible navigation links to relevant product categories/catalog and the cart.
- Mobile-friendly presentation that avoids overflow and keeps critical destinations reachable.

As there is no JavaScript or back end, search and account features are **visual affordances only**, unless they can be implemented meaningfully with plain HTML. Do not promise real search results or authentication.

### Main content

- **Hero section:** prominent campaign, highlighted drone, or brand message, with a clear link to catalog or the featured product.
- **New Arrivals:** horizontal set of product cards; on mobile, cards should remain readable and be accessible via a simple responsive layout or native horizontal scrolling.
- **Best Sellers:** second horizontal product-card section with the same core card design.
- Product cards should have an image, descriptive name, useful short detail, price where available, and a clear link to `product.html` (the prototype's sample product page).

### Footer

- **Categories:** drones, camera drones, accessories, and other relevant Zephyr product categories.
- **Legal:** terms and conditions, privacy policy, and about Zephyr.
- **Contact:** suitable contact details or a clearly labeled placeholder, without inventing live support channels.

Do not leave decorative links pointing to `#` as though they are functional. Where a legal/account destination is outside the five required pages, label it as nonfunctional prototype content or provide a meaningful alternative; do not create extra pages unless the team agrees.

---

## 6. Required View: Catalog (`catalog.html`)

- Reuse the common header and footer.
- Provide a visible **filter bar before the product grid**.
- Include category and size filtering controls as the assignment requires. Since drones are not clothing, interpret **size** as a clearly explained drone size class (for example: compact, medium, large); do not use apparel sizes.
- Organize a **reference set of 20 visible products**, arranged **four columns by five rows on desktop**.
- Adapt the grid to fewer columns on tablet and mobile (for example, two and one columns respectively) without horizontal page overflow.
- Each product card includes a thumbnail, product name, concise attributes, price when specified, and a link to `product.html`.
- Use only categories defined in the separate product-data file; do not invent categories to fill the grid.

**Static-only limitation:** Native HTML select controls may demonstrate the filter interface, but **they must not be described as functioning product filters** unless the team develops an HTML-only, genuinely usable alternative. No client-side product filtering with JavaScript is permitted. A static prototype with visually complete controls meets the demonstration intent; clearly document this behavior.

---

## 7. Required View: Product Details (`product.html`)

- Reuse the common header and footer.
- Desktop layout: **two main columns** — left product image occupying approximately half of the content width; right product details and purchase controls.
- Mobile layout: stack image above details with good spacing and readable typography.
- Display product **name, code/reference, size class, price, quantity selector, and “Add to cart” button**.
- Provide an additional **detailed description** below the main product area, covering materials/build characteristics and recommended scenarios or use cases.
- Show relevant product characteristics and use cases only when supported by the separate product-data file.
- Label the product image accessibly and use a meaningful page heading.

**Static-only limitation:** Quantity controls may be native HTML inputs. “Add to cart” may navigate to the populated sample `cart.html` as a **demonstration** of the intended flow; it does **not** actually store a selected item or quantity. The UI and documentation must not claim persistent cart state.

---

## 8. Required View: Cart (`cart.html`)

- Show a **full-page cart** rather than a slide-out drawer.
- Reuse the common header and footer.
- Show **three distinct example cart items** selected from the separate product-data file so reviewers can assess the layout; do not define those items here.
- For each cart line, show a product thumbnail, product name/reference, unit price, displayed quantity, and line total.
- Include a clearly separated order summary showing **subtotal, tax, and total**.
- Provide an obvious **“Purchase”** action linking to `checkout.html`.
- Totals must be **arithmetically consistent** with the values selected from the separate product-data file, the demonstrated quantities, and the displayed tax method. If tax is illustrative, label the rate/amount as an estimate and avoid pretending it is a live tax quote.
- On small screens, stack cart rows and move the summary underneath or alongside when space permits.

**Static-only limitation:** Cart contents and totals are illustrative prototype displays, populated using the separate product-data source. Without JavaScript or a back end, changing an input does not recompute totals or update stored cart contents; avoid misleading interactive affordances. If an editable quantity field is shown to satisfy layout expectations, label its prototype status.

---

## 9. Required View: Checkout (`checkout.html`)

Present a clearly numbered **three-step checkout flow**:

1. **Personal details** — e.g., full name, email address, and phone (if needed).
2. **Shipping address** — e.g., street address, apartment/unit, city, state/region, postal code, and country.
3. **Card payment** — visually demonstrate cardholder name, card number, expiration date, and security-code fields.

Requirements:

- Reuse the common header and footer.
- Show the order of the three steps clearly. An accessible **single HTML page with three numbered fieldsets/sections** is acceptable and recommended for a static prototype; do not invent an interactive wizard that requires JavaScript.
- Use native `<form>`, `<fieldset>`, `<legend>`, `<label>`, and appropriate input types/autocomplete attributes where useful.
- Group and label inputs clearly, and provide visible focus states, required field indicators, and explanatory text where needed.
- Keep forms usable on narrow screens, with readable input widths and sufficient touch-target spacing.
- Provide a clearly labeled **demo-only final action**. **No real charges, card processing, order submission, or storage of personal/payment data.** Do not point the form at an unverified external endpoint; avoid collecting real card numbers in a public deployed prototype. Use mock or disabled payment fields and visible demo-data guidance as appropriate.

The checkout page is a **layout and usability demonstration**, not a PCI-compliant payment system.

---

## 10. Technical Constraints — Mandatory

**Allowed:**

- Semantic **HTML5**.
- **Tailwind CSS** for styling and responsive utility classes.
- Minimal supplementary CSS if truly necessary and consistent with the style guide.
- Static images and other appropriately licensed assets.
- **Non-executable Schema.org JSON-LD** in `<script type="application/ld+json">` blocks.
- Git/GitHub for teamwork.

**Not allowed:**

- Executable JavaScript, including custom scripts and JavaScript-based UI behavior.
- React, Vue, Angular, Svelte, Next.js, or other frontend frameworks.
- Bootstrap or additional unrelated CSS/UI frameworks.
- Back-end APIs, databases, authentication systems, real cart persistence, or payment processing.
- JavaScript widgets for filtering, step navigation, quantity calculations, dropdowns, or carousels.
- Unapproved technology additions suggested by an AI assistant.

A Tailwind build process can be used by the team **only to produce CSS**; it does not authorize JavaScript in the delivered site. Prefer an optimized production Tailwind CSS output for the deployed prototype rather than assuming development-only tooling is suitable for performance testing.

When functionality cannot be implemented honestly with static HTML, **show the intended interface, keep navigation useful, and explicitly mark the behavior as a prototype**. Do not secretly expand the stack to simulate it.

---

## 11. Semantic HTML and Accessibility

- Use `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, and `<form>` when semantically appropriate.
- Include one clear primary `<h1>` per page and a logical descending heading hierarchy.
- Use descriptive link text and meaningful labels for all form inputs.
- Use `<button>` only for genuine actions and `<a>` for navigation; avoid clickable `<div>` elements.
- Prefer native semantics over unnecessary ARIA; label distinct navigation regions when useful.
- Add a **“Skip to main content”** link and a stable main-content target on each page.
- Ensure full keyboard access, visible focus indication, usable native form elements, and logical tab order.
- Give meaningful product images informative `alt` text; use empty `alt` for purely decorative images.
- Maintain adequate text/button contrast according to the separate style guide and accessibility requirements.
- Do not communicate information only through color, icons, movement, or images.
- Respect reduced-motion preferences for optional animations and avoid distracting movement.
- Ensure text remains legible when zoomed and controls do not overlap or disappear.
- Do not use unnecessary fixed heights, especially for content-heavy pages.

---

## 12. Responsive Layout Requirements

All five views must be tested at mobile, tablet, and desktop widths.

- Start with mobile-first Tailwind utility classes, then expand layouts using appropriate responsive variants.
- **Home:** readable hero and product cards; horizontal product sets should not create page-level overflow.
- **Catalog:** one or two columns on narrow screens, progressively increasing to four desktop columns.
- **Product:** stacked product imagery and information on mobile; two-column layout on desktop.
- **Cart:** item rows reflow cleanly; summary stays visible and understandable.
- **Checkout:** labels and fields remain readable; columns collapse when needed.
- Shared navigation, footer, images, and buttons must adapt naturally at all breakpoints.
- No unintended horizontal scrolling, clipped information, overlapping elements, or unusably small controls.

---

## 13. SEO and Schema.org

For **each HTML file**:

- Set the correct `lang` attribute, UTF-8 character encoding, and viewport meta tag.
- Use a unique, descriptive `<title>` and relevant meta description.
- Maintain semantic landmarks, readable body text, descriptive headings, and descriptive links.
- Use appropriate descriptive image `alt` text and sensible image file names.
- Link views using crawlable HTML `<a href="...">` elements.
- Use accurate, useful product names/descriptions from the separate product-data file rather than inventing content or keyword stuffing.
- Avoid misleading claims or content written only to manipulate ranking.

**Structured data:**

- **Home:** `Organization` for Zephyr, using only verified organization properties.
- **Product page:** `Product` information matching the visible product, using only accurate properties supplied by the separate product-data file; omit unverified fields.
- **Catalog:** `ItemList` may be used if its contents accurately reflect the rendered products; it is optional.
- Use JSON-LD only as structured metadata, not executable JavaScript.
- Do not invent business addresses, reviews, ratings, availability, certifications, or official brand relationships in structured data.
- Validate metadata using appropriate Schema.org and search-engine testing tools when possible.

Clear, human-readable information can also improve AI/search-system understanding, but this must not conflict with SEO integrity or the HTML + Tailwind restriction.

---

## 14. Images, Content, and Performance

- Use relevant, high-quality, appropriately licensed drone/product imagery.
- Keep assets local under `assets/images/` where practical; avoid unstable external image hotlinks.
- Compress oversized images; prefer WebP/AVIF when appropriate.
- Use responsive image sizing and width/height attributes (or equivalent space reservation) to reduce layout shift.
- Consider lazy loading below-the-fold imagery; prioritize the hero/important above-the-fold image.
- Do not load unnecessary fonts, scripts, libraries, or animation assets.
- Minimize generated Tailwind CSS and avoid excessive custom CSS.
- Test the **deployed public URL** in [PageSpeed Insights](https://pagespeed.web.dev/), on mobile and desktop where available.
- **Performance acceptance:** >=80 required; >=90 preferred. Record measured results honestly rather than claiming an untested score.

---

## 15. Collaboration and Git Workflow

Two developers will share responsibility for the project. Use a workflow that keeps changes reviewable and reduces merge conflicts.

1. **Never implement features directly on `main`.** Start work in a dedicated branch such as `feature/shared-layout`, `feature/home`, `feature/catalog`, `feature/product`, `feature/cart`, or `feature/checkout`.
2. **Divide work by page or feature.** Coordinate edits to common navigation, footer, Tailwind configuration, and shared assets so both contributors do not overwrite one another.
3. **Commit frequently**, with one logical change per commit and descriptive messages, such as `Add responsive catalog grid` or `Build checkout form sections`.
4. **Sync before opening a PR.** Fetch the latest changes and incorporate `main` into the feature branch using the team's agreed merge/rebase method (for example `git fetch origin` followed by `git merge origin/main`; or an agreed `git pull origin main`). Test again after syncing.
5. **Open a pull request for each major view or shared feature**, describing the change, files touched, screenshots/testing completed, and known static-prototype limitations.
6. **Review and merge PRs into `main`** after feedback and conflict resolution. Resolve conflicts together; never force-push or overwrite a teammate's work without agreement.
7. **Verify integration** after merging: check all cross-page links, consistency of shared markup, responsive layouts, and the deployed site.

### Suggested responsibility split

- **Developer A:** shared site layout, home, and catalog.
- **Developer B:** product details, cart, and checkout.
- **Both:** plan content/navigation, review each other's PRs, handle shared styling, test responsiveness and accessibility, and perform final QA.

This is only a suggested split; the team may choose a different balanced allocation.

---

## 16. Testing and Acceptance Checklist

### Required pages and user journey

- [ ] `index.html`, `catalog.html`, `product.html`, `cart.html`, and `checkout.html` exist.
- [ ] Every page uses the same intended header and footer structure.
- [ ] Links between the five pages work correctly with relative URLs.
- [ ] Home contains navbar, hero, New Arrivals, Best Sellers, and required footer groups.
- [ ] Catalog contains category and size-class filter UI and **20 product cards**, displayed 4x5 on desktop.
- [ ] Product page contains image/details columns, name, reference, size, price, quantity, Add to cart, materials, and use cases.
- [ ] Cart displays **three sample products**, their prices/quantities/line totals, subtotal, tax, total, and Purchase link.
- [ ] Checkout presents personal details, shipping address, and mock card-payment steps.
- [ ] Static-only behaviors and demo-only checkout are clear to reviewers.

### Technical and visual quality

- [ ] The frontend uses **HTML + Tailwind CSS only**, with no executable JavaScript or additional frontend framework.
- [ ] Design follows the separate style guide without duplicating it here.
- [ ] All pages use meaningful semantic landmarks, headings, and valid HTML.
- [ ] Forms have associated labels and sensible field grouping.
- [ ] Keyboard navigation, focus states, image alternatives, and text contrast are tested.
- [ ] Mobile/tablet/desktop layouts are usable with no unintended horizontal overflow.
- [ ] Each page has appropriate SEO metadata and indexable HTML content.
- [ ] Relevant Schema.org metadata is accurate and consistent with visible content.
- [ ] Assets are optimized and sourced appropriately.
- [ ] A publicly accessible deployed URL is tested using PageSpeed Insights.
- [ ] PageSpeed score is **80 or higher**, with **90+ preferred**.

### Git and teamwork

- [ ] Contributors use feature branches rather than working on `main`.
- [ ] Each major feature/page has its own PR or an agreed equivalent reviewable PR.
- [ ] Commit history uses meaningful messages.
- [ ] Feature branches are synchronized with `main` before review/merge.
- [ ] Merge conflicts are discussed and resolved collaboratively.
- [ ] Final merged project is reviewed by both teammates.

---

## 17. Instructions for AI Copilots and Contributors

**Read this full product context and the separate style guide before changing any project files.** Then inspect the current repository to avoid replacing existing work.

Before implementation, briefly explain:

1. Which view or feature is being built.
2. Which files will change.
3. The proposed semantic HTML structure.
4. How Tailwind responsive classes will handle mobile, tablet, and desktop.
5. The accessibility and SEO considerations.
6. Which interactions are real HTML navigation and which are **visual-only prototypes**.
7. Any shared-component or Git merge implications.

During implementation:

- Stay strictly within HTML + Tailwind CSS.
- Follow the existing style guide rather than creating new design tokens here.
- Favor clean, understandable markup over unnecessary wrappers or abstractions.
- Reuse consistent header/footer markup across the five pages.
- Read and use the existing separate product-data file for all product content; never place product records into this context file or manufacture missing records.
- Keep verified content readable and structured for search engines and people.
- Do not invent functional cart state, live filtering, authentication, payment processing, or other JavaScript/back-end behavior.
- Do not copy DJI's source code or branded assets.
- Make changes incrementally, test before committing, and keep PRs focused.
- **Do not add technologies or features beyond the assignment without team agreement.**

**Definition of success:** A cohesive, polished Zephyr storefront prototype with five linked views, responsive Tailwind layouts, sound semantic HTML, truthful SEO/Schema.org metadata, accessible interactions, clear demo-only limitations, PageSpeed testing, and evidence of collaborative Git practices.
