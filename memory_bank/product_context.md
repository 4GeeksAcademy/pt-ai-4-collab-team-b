# Zephyr — Product Context

## 1. Project Overview

**Zephyr is a responsive, multi-page drone e-commerce prototype** commissioned by Zephyr and being developed under contract by a six-person web development team. The team is responsible for delivering a cohesive, review-ready storefront prototype that meets Zephyr’s requirements and quality standards.

The project takes DJI's existing drone shopping experience as a **reference for product categories, page structure, and shopping journeys**, then proposes a clearer, more modern, easier-to-navigate refresh under the **Zephyr** name. The goal is not to clone DJI's website or imply an official affiliation; it is to demonstrate thoughtful improvements in information hierarchy, discoverability, product comparison, responsiveness, and checkout clarity.

**Technology restriction from the beginning: build with semantic HTML and Tailwind CSS only.** No React, Vue, Angular, Bootstrap, JavaScript-driven UI, back-end services, payment integrations, or other advanced technologies. Git and GitHub are used for collaboration and version control, not as application technologies. Schema.org JSON-LD is permissible as *non-executable structured metadata*.

The deliverable is a **visual and navigable prototype**, not a production e-commerce platform. Every required view must exist as an individual HTML file, link correctly to the others, and demonstrate the intended user journey without pretending that static pages provide real shopping or payment functionality.

---

## 2. Primary Goals

- Present Zephyr as a polished and trustworthy drone storefront.
- Improve on the reference site's usability through clear navigation, readable information, and well-organized product cards.
- Help visitors discover drones, browse by relevant attributes, and understand product capabilities.
- Demonstrate an understandable journey from the home page to catalog, product details, cart, and checkout, with an accessible Support destination.
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

Provide these six linked HTML pages:

| View | File | Purpose |
| --- | --- | --- |
| Home | `index.html` | Introduce Zephyr, feature campaigns, new arrivals, and best sellers. |
| Catalog | `catalog.html` | Display and visually organize a reference set of 20 products. |
| Product details | `product.html` | Show one drone or accessory with essential purchasing information. |
| Cart | `cart.html` | Display three sample items and a purchase summary. |
| Checkout | `checkout.html` | Present a three-step checkout flow as a visual prototype. |
| Support | `support.html` | Show a contact support form and short FAQ section. |

Include `product_context.md`, the existing separate style guide, a shared Tailwind stylesheet or Tailwind setup appropriate to the team's environment, and locally stored assets when practical.

Suggested repository organization (adapt to the existing repo rather than creating duplicate files):

```text
/
├── index.html
├── catalog.html
├── product.html
├── cart.html
├── checkout.html
├── support.html
├── product_context.md
├── assets/
│   └── images/
└── ... shared Tailwind source/output and existing style guide
```

**All navigation must work with ordinary relative HTML links.** The six HTML files must be reachable from each other through appropriate navigation links or calls to action. Avoid dead-end pages.

### Product data ownership (separate source of truth)

**This document defines requirements, layout, behavior, and quality standards only. It must not contain product data.** The team maintains all product records in a separate, existing data file. Contributors and AI assistants must find and read that file before populating product-related content in any HTML page.

- Do not add product names, models, prices, descriptions, technical specifications, product images/paths, inventory status, or fabricated sample records to `product_context.md`.
- Do not create a competing dataset, duplicate the separate data file, or silently replace missing entries with invented values.
- Use product information from the separate file consistently across home cards, catalog cards, product details, cart examples, and any product-related Schema.org markup.
- The **20 catalog cards** and **three cart line items** are client-approved layout requirements, not data definitions. Populate them from the separate file when sufficient records are available; otherwise flag the gap to the team without fabricating product content.
- If data-file location, field names, or values are unclear, inspect the repository and existing team documentation. Treat the separate file as authoritative and leave it unchanged unless explicitly asked to modify it.

### Shared page elements

The header/navigation and footer must look and behave consistently on **every** view, including Support. Provide a working route to `support.html` in the shared navbar or footer. Because this is an HTML-only prototype, shared components can be repeated as consistent HTML markup across files; do not introduce a templating engine, React components, or JavaScript solely to implement reuse. Keep the repeated markup synchronized during code review.

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

### Required structure

- Reuse the shared navbar and footer defined in Section 3.
- Include a primary page heading and a prominent **hero** highlighting a Zephyr campaign, product, or brand message.
- Include two distinct horizontal product-card sections: **New Arrivals** and **Best Sellers**.
- Each product card should display an image, a name, useful brief context, price when available, and a link to `product.html`.
- Source all product content from the separate product-data file, not this document.

### Page-specific components and behavior

- Hero call to action must link to a relevant working page such as `catalog.html` or `product.html`.
- Horizontal product sections may use native scrolling or responsive wrapping; do not introduce JavaScript carousels.
- Search and account affordances are visual only unless genuinely usable with static HTML. Do not imply that account or search services exist.

### Responsive design

- Keep the hero readable and appropriately sized on mobile, tablet, and desktop.
- Maintain usable card widths and avoid page-level horizontal overflow.
- Preserve accessible navigation and calls to action at every breakpoint.

### Accessibility and semantic HTML

- Use a meaningful `<h1>` for the page, `<section>` headings for product groups, and `<article>` where suitable for individual product cards.
- Ensure hero text is real HTML text rather than embedded solely in an image.
- Provide descriptive links, image alternatives, and visible focus states.

### Definition of done

- [ ] Hero and working call to action are present.
- [ ] New Arrivals and Best Sellers each show coherent product cards from the separate data file.
- [ ] Shared navbar and footer are present, including a link to Support.
- [ ] Layout is responsive and keyboard accessible.
- [ ] No simulated search/account behavior is misrepresented as live functionality.

---

## 6. Required View: Catalog (`catalog.html`)

### Required structure

- Reuse the shared navbar and footer.
- Place a filter bar **before** the product grid, including **category** and **size** controls.
- Display **20 product cards** as a **4-column × 5-row grid on desktop**, when the data file has sufficient records.
- Product cards should include image, name, concise relevant information, price when available, and a link to `product.html`.

### Page-specific components and behavior

- Treat **size** as a drone size class, rather than apparel sizing; use only categories and attributes supported by the separate data file.
- Native `<select>` elements can illustrate filtering, but without JavaScript or server processing they **do not dynamically filter products**. Clearly identify static controls as prototype-only.
- Do not manufacture products or categories to fill the grid. If fewer than 20 valid records exist, flag the data gap for the team.

### Responsive design

- Use a responsive grid, with fewer columns at tablet and mobile widths; aim for four columns on desktop.
- Avoid cropped text, oversized images, or page-level horizontal overflow.
- Keep filter controls readable and easy to operate on small screens.

### Accessibility and semantic HTML

- Use a meaningful `<h1>`, a labeled filter `<form>` or grouping, and semantic product-card content.
- Associate labels with filter controls and ensure meaningful image alternatives.
- Use actual anchors for product navigation and retain visible keyboard focus indicators.

### Definition of done

- [ ] Category and size-class controls appear above the product grid.
- [ ] Up to 20 data-backed product cards appear in a 4×5 desktop reference layout.
- [ ] Every product card links to the prototype product-details page.
- [ ] Filter limitations are disclosed rather than described as functioning dynamically.
- [ ] Responsive behavior, semantic markup, and keyboard access are verified.

---

## 7. Required View: Product Details (`product.html`)

### Required structure

- Reuse the shared navbar and footer.
- Create a **two-column desktop layout**, with product imagery occupying roughly half of the available width on the left and product details on the right.
- Display **name, code/reference, size, price, quantity selector, and Add to cart** action.
- Include a detailed description section below the primary layout covering **materials/build** and **recommended uses or wearing-equivalent use cases** relevant to a drone or accessory.
- All product fields must come from the separate product-data file; do not define records here.

### Page-specific components and behavior

- Use native HTML quantity input controls where appropriate.
- The Add to cart action may link to `cart.html` to demonstrate the shopping journey; it does **not** actually save the chosen product or quantity.
- Display only descriptions, material details, and use scenarios supported by the separate data file; flag absent fields rather than fabricating them.

### Responsive design

- Stack imagery before details on small screens and use two columns on wider screens.
- Keep the quantity field, price, and Add to cart action visible and usable without clipping.
- Scale imagery naturally while preserving its aspect ratio.

### Accessibility and semantic HTML

- Use the product name as the main `<h1>` and appropriate section headings for details.
- Provide informative image `alt` text and an explicit label for quantity.
- Use links for actual page navigation; do not imply that a cart-state update occurs.

### Definition of done

- [ ] Desktop two-column and mobile stacked layouts are present.
- [ ] Required product fields and quantity selector are visible.
- [ ] Add to cart leads to the sample cart and is described honestly as a prototype action.
- [ ] Description includes data-backed materials/build and use scenarios where available.
- [ ] Shared navigation, semantic structure, and keyboard accessibility are verified.

---

## 8. Required View: Cart (`cart.html`)

### Required structure

- Reuse the shared navbar and footer.
- Implement a **full-page cart**, not a drawer or side panel.
- Show **three example line items** from the separate product-data file, if available.
- Each item must show a **thumbnail, product identity, unit price, quantity, and line total**.
- Include an order summary with **subtotal, tax, total**, and a **Purchase** action linking to `checkout.html`.

### Page-specific components and behavior

- Calculate displayed line totals and summary values consistently using the selected source data and illustrated quantities.
- Label estimated tax clearly; do not imply a live tax calculation or jurisdiction-specific accuracy.
- Because this is HTML-only, edits to quantity cannot persist or automatically recalculate totals. Display quantities as illustrative values or clearly label any editable inputs as demo-only.
- If there are insufficient records for three distinct items, report the gap instead of inventing item data.

### Responsive design

- Allow cart rows to stack or reflow while retaining clear labels for price, quantity, and totals.
- Position the summary beside items on roomy screens and below them on narrow screens.
- Avoid cramped layouts or off-screen actions.

### Accessibility and semantic HTML

- Use a main heading, meaningful item groupings, and clear order-summary labels.
- Give meaningful image alternatives and ensure the Purchase link is keyboard accessible.
- Do not rely solely on visual position or color to communicate totals.

### Definition of done

- [ ] Full-page cart shows three data-backed demonstration products, subject to source availability.
- [ ] Each line displays image, unit price, quantity, and line total.
- [ ] Summary displays arithmetically consistent subtotal, estimated tax, and total.
- [ ] Purchase link opens `checkout.html`.
- [ ] Responsive layout and static-cart disclosure are present.

---

## 9. Required View: Checkout (`checkout.html`)

### Required structure

- Reuse the shared navbar and footer.
- Present a **three-step checkout flow** in order:
  1. **Personal details** — name, email, and other relevant contact fields.
  2. **Shipping address** — street, unit (optional), city, region, postal code, and country.
  3. **Card payment** — visual cardholder, card number, expiration, and security-code fields.
- A single semantic HTML form divided into three visibly numbered sections or `<fieldset>` groups is recommended over a JavaScript wizard.

### Page-specific components and behavior

- Include labels, suitable input types, `autocomplete` values, and appropriate native validation attributes.
- Provide a clearly labeled **demo-only final action**, not a real payment button connected to a processor.
- Never transmit, collect, persist, or invite entry of real payment card data; use mock/disabled card inputs or clearly non-collecting illustrative fields.
- Do not invent a payment backend, multi-step form engine, or order confirmation workflow.

### Responsive design

- Stack fields on small screens and use columns only where they improve readability.
- Keep labels, helper text, step indicators, and final action usable on mobile, tablet, and desktop.
- Prevent clipped inputs and horizontal scrolling.

### Accessibility and semantic HTML

- Use `<form>`, `<fieldset>`, `<legend>`, `<label>`, and native inputs meaningfully.
- Explain required fields in text and preserve visible focus states.
- Keep step order understandable without CSS, scripting, or visual cues alone.

### Definition of done

- [ ] All three steps are visible in the correct order.
- [ ] Personal, shipping, and mock payment fields are clearly labeled.
- [ ] Form remains legible and navigable on mobile and desktop.
- [ ] No real transaction, card-data collection, or misleading order submission occurs.
- [ ] Shared header/footer, semantic structure, and accessible focus are verified.

---

## 10. Required View: Support (`support.html`)

### Required structure

- Reuse the shared navbar and footer.
- Include a clear page heading: **Support**.
- Organize the main content into two sections: **Contact Support** and **Frequently Asked Questions (FAQ)**.

### Page-specific components and behavior

- **Contact Support form** with:
  - **Name** — required text input.
  - **Email** — required email input with native HTML validation.
  - **Message** — required multiline `<textarea>`.
  - **Submit** — clearly labeled action showing the intended form workflow.
- Use a non-submitting/static demonstration of the form, since no backend or JavaScript form handling is allowed. Do not imply that support messages are actually delivered or store visitor entries.
- Include **4–6 short FAQ question-and-answer pairs** covering general questions about shopping, shipping, returns, and technical support.
- FAQ content must come from the team's approved content or policy sources where specifics are involved. Do not invent shipping guarantees, return terms, warranties, support promises, or product specifications.
- Use ordinary visible question/answer sections or native `<details>` and `<summary>` for accessible HTML-only expansion.

### Responsive design

- Contact form and FAQ may appear beside one another on wider screens; stack them on mobile.
- Ensure comfortable spacing, readable answers, and usable form controls at every breakpoint.
- Avoid clipped fields or unintended horizontal overflow.

### Accessibility and semantic HTML

- Use `<main>`, `<section>`, semantic headings, `<form>`, `<label>`, `<input>`, `<textarea>`, and an appropriate button.
- Associate each form field with a visible label; do not rely on placeholders alone.
- Preserve keyboard access, clear focus states, and native FAQ disclosure behavior where used.

### Definition of done

- [ ] `support.html` exists and is linked from shared navigation or footer.
- [ ] Contact form shows Name, Email, Message, and Submit controls.
- [ ] Four to six accessible FAQs appear with approved, non-invented answers.
- [ ] Prototype-only submission behavior is clear.
- [ ] Responsive design, semantic HTML, and keyboard access are verified.

---

## 11. Technical Constraints — Mandatory

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

## 12. Semantic HTML and Accessibility

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

## 13. Responsive Layout Requirements

All six views must be tested at mobile, tablet, and desktop widths.

- Start with mobile-first Tailwind utility classes, then expand layouts using appropriate responsive variants.
- **Home:** readable hero and product cards; horizontal product sets should not create page-level overflow.
- **Catalog:** one or two columns on narrow screens, progressively increasing to four desktop columns.
- **Product:** stacked product imagery and information on mobile; two-column layout on desktop.
- **Cart:** item rows reflow cleanly; summary stays visible and understandable.
- **Checkout:** labels and fields remain readable; columns collapse when needed.
- **Support:** contact form and FAQs stack appropriately and keep controls readable.
- Shared navigation, footer, images, and buttons must adapt naturally at all breakpoints.
- No unintended horizontal scrolling, clipped information, overlapping elements, or unusably small controls.

---

## 14. SEO and Schema.org

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

## 15. Images, Content, and Performance

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

## 16. Collaboration, Page Ownership, and Git Workflow

The Zephyr contract is delivered by **six developers, with exactly one primary owner per required page**. Each developer is accountable for implementing, testing, and documenting their assigned view. All six developers remain jointly responsible for a unified storefront experience and successful integration.

### Page ownership

| Owner | Assigned view | Primary file | Suggested branch |
| --- | --- | --- | --- |
| Developer 1 | Home | `index.html` | `feature/home` |
| Developer 2 | Catalog | `catalog.html` | `feature/catalog` |
| Developer 3 | Product details | `product.html` | `feature/product` |
| Developer 4 | Cart | `cart.html` | `feature/cart` |
| Developer 5 | Checkout | `checkout.html` | `feature/checkout` |
| Developer 6 | Support | `support.html` | `feature/support` |

The table assigns **page ownership, not individual identities**. The team should associate each role with its designated developer through its own project-management process. A page owner maintains that page and addresses review feedback; other developers should not modify another owner's page without coordinating first.

### Shared responsibilities and integration

- **Shared navigation and footer:** Agree on structure, link destinations, accessibility, and Tailwind class conventions before building individual pages. Each page owner implements the same approved markup within their own HTML file, since no JavaScript or templating engine is permitted.
- **Shared styles and assets:** Follow the existing style guide and Tailwind setup. Designate a coordinator for changes to shared configuration, styles, and common assets; the coordinator is a *cross-cutting responsibility*, not a seventh page owner.
- **Product data:** Use the separate product-data file as the single source of truth. Coordinate changes with the appropriate data-file maintainer and do not add product records to this document.
- **Navigation and integration:** Validate transitions between all six pages, including Home → Catalog → Product → Cart → Checkout and access to Support.
- **Reviews:** Every page PR should be reviewed by at least one other team member. Cross-page or shared-file changes should be reviewed by affected page owners.
- **Final QA:** All six developers participate in testing the integrated site for responsiveness, accessibility, SEO, consistency, and performance.

### Git and pull-request workflow

1. **Do not commit feature work directly to `main`.** Each page owner works in the dedicated feature branch listed above. Use separate focused branches such as `feature/shared-layout` for explicitly coordinated shared work.
2. **Keep page ownership clear.** Make changes primarily in your assigned HTML file. Discuss modifications to the shared stylesheet, Tailwind configuration, navigation conventions, or another owner's page before changing them.
3. **Commit often** with one logical change per commit and descriptive messages, such as `Build responsive support form` or `Add catalog filter layout`.
4. **Synchronize with `main` before requesting review.** Fetch and incorporate current `main` into your branch using the team's agreed merge or rebase process; test again afterward.
5. **Open at least one pull request for each of the six pages.** Explain the scope, files changed, screenshots or testing evidence, and any known static-prototype limitations. Open separate PRs for substantial shared-feature changes.
6. **Resolve conflicts collaboratively.** Do not force-push over teammates' work, bypass reviews, or overwrite another person's changes without agreement.
7. **Merge approved work and retest integration.** Verify shared navbar/footer consistency, cross-page links, responsive layouts, and the deployed public URL after the six page branches are merged.

The objective is **six clearly owned pages that function together as one coherent Zephyr website**, not six visually or structurally disconnected deliverables.
---

## 17. Testing and Acceptance Checklist

### Required pages and user journey

- [ ] `index.html`, `catalog.html`, `product.html`, `cart.html`, `checkout.html`, and `support.html` exist.
- [ ] Every page uses the same intended header and footer structure.
- [ ] Links between the six pages work correctly with relative URLs.
- [ ] Home contains navbar, hero, New Arrivals, Best Sellers, and required footer groups.
- [ ] Catalog contains category and size-class filter UI and **20 product cards**, displayed 4x5 on desktop.
- [ ] Product page contains image/details columns, name, reference, size, price, quantity, Add to cart, materials, and use cases.
- [ ] Cart displays **three sample products**, their prices/quantities/line totals, subtotal, tax, total, and Purchase link.
- [ ] Checkout presents personal details, shipping address, and mock card-payment steps.
- [ ] Support contains a labeled Name/Email/Message form and 4–6 FAQs.
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
- [ ] Each of the six pages has one designated primary developer and at least one reviewed PR.
- [ ] Commit history uses meaningful messages.
- [ ] Feature branches are synchronized with `main` before review/merge.
- [ ] Merge conflicts are discussed and resolved collaboratively.
- [ ] All six developers participate in final integration review and QA.

---

## 18. Instructions for AI Copilots and Contributors

**Read this full product context and the separate style guide before changing any project files.** Confirm your assigned page, check the six-person ownership matrix, and inspect the repository to avoid replacing existing work.

Before implementation, briefly explain:

1. Which assigned view or coordinated shared feature is being built, and who owns it.
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
- Reuse consistent header/footer markup across the six pages.
- Read and use the existing separate product-data file for all product content; never place product records into this context file or manufacture missing records.
- Keep verified content readable and structured for search engines and people.
- Do not invent functional cart state, live filtering, authentication, payment processing, or other JavaScript/back-end behavior.
- Do not copy DJI's source code or branded assets.
- Work on your own feature branch, respect the designated page owner, make changes incrementally, test before committing, and keep PRs focused.
- **Do not add technologies or features beyond the agreed contract scope without team agreement.**

**Definition of success:** A cohesive, polished Zephyr storefront prototype with six linked views, responsive Tailwind layouts, sound semantic HTML, truthful SEO/Schema.org metadata, accessible interactions, clear demo-only limitations, PageSpeed testing, and evidence of coordinated work by six page owners using reviewed Git pull requests.
