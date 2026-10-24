# Product Context

## Project Overview

Build a modern, accessible, single-page website for an artist who needs an
online presence to showcase their identity, career, creative work, and
upcoming shows.

The website should feel polished, artistic, warm, and professional while
remaining easy to navigate, accessible to assistive-technology users,
understandable by search engines, and performant.

The project must be built using HTML and CSS only.

---

## Primary Goals

The website should:

- Introduce the artist and their identity.
- Present information about the artist's career and creative work.
- Display upcoming shows or performances.
- Allow users to navigate easily between major sections.
- Use semantic HTML.
- Follow accessibility best practices.
- Be optimized for search-engine indexing.
- Include appropriate Schema.org structured data.
- Support good SEO and general AI/GEO discoverability.
- Use responsive, maintainable CSS.
- Perform well in PageSpeed Insights.

---

## Required Files

The project should include:

- `index.html`
- `styles.css`
- `product_context.md`

Recommended asset structure:

```text
assets/
└── images/
```

Images should be stored locally when practical rather than relying on
unstable third-party image URLs.

---

# Technical Constraints

Use:

- HTML
- CSS

Do NOT use:

- Executable JavaScript
- React
- Vue
- Angular
- Bootstrap
- Tailwind
- CSS frameworks
- JavaScript libraries
- Frontend frameworks
- Premade website templates

Schema.org JSON-LD may be included using:

```html
<script type="application/ld+json">
```

This is structured metadata and must not contain executable JavaScript.

---

# Required Page Structure

The website must be a single-page experience containing:

1. Header
2. Navigation bar
3. Hero / Welcome section
4. About Me section
5. Career section
6. Upcoming Shows section
7. Footer

The main navigation should allow users to move directly to major sections
using anchor links.

Suggested IDs:

- `#about`
- `#career`
- `#shows`

Example:

```html
<a href="#about">About Me</a>
<a href="#career">Career</a>
<a href="#shows">Upcoming Shows</a>
```

Navigation must work without JavaScript.

Major sections should occupy approximately the full height of a typical
computer viewport where appropriate.

Prefer:

```css
min-height: 100vh;
```

rather than a fixed height so content is not clipped.

---

# Visual Direction

The website should feel:

- Modern
- Artistic
- Warm
- Elegant
- Professional
- Visually cohesive

Avoid a generic template appearance.

Use whitespace, typography, imagery, color, and layout intentionally to
create a strong visual hierarchy.

---

# Color Theme

Use the following Realtime Colors palette:

```css
:root {
  --text: #17060c;
  --background: #fdf8f9;
  --primary: #cd436a;
  --secondary: #e19d90;
  --accent: #d8996d;
}
```

## Recommended Usage

### `--text: #17060c`

Use for:

- Body text
- Headings
- Navigation text
- Important information

### `--background: #fdf8f9`

Use as the primary page background.

### `--primary: #cd436a`

Use for:

- Primary calls to action
- Buttons
- Borders
- Important highlights
- Major design accents

Avoid using the primary color as small text on the main background because
the contrast is slightly below the WCAG AA 4.5:1 target for normal text.

### `--secondary: #e19d90`

Use for:

- Supporting section backgrounds
- Cards
- Secondary visual elements

Use dark `--text` on this color when text is present.

### `--accent: #d8996d`

Use for:

- Decorative details
- Borders
- Badges
- Supporting highlights

Use dark `--text` on this color when text is present.

---

# Color Accessibility

Accessibility takes priority over aesthetics.

Maintain sufficient contrast for:

- Body text
- Headings
- Navigation
- Links
- Buttons
- Calls to action
- Focus indicators
- Show information

Do not communicate important information through color alone.

Interactive states may combine color with:

- Underlines
- Borders
- Background changes
- Focus outlines
- Other visible changes

---

# Semantic HTML

Use semantic HTML throughout the page.

Prefer elements such as:

- `<header>`
- `<nav>`
- `<main>`
- `<section>`
- `<article>`
- `<footer>`
- `<h1>`
- `<h2>`
- `<h3>`
- `<p>`
- `<a>`
- `<img>`
- `<time>`

Do not build the page primarily from generic `<div>` elements when a
semantic element provides the correct meaning.

Generic `<div>` elements may still be used for layout or styling when no
more meaningful element exists.

---

# Heading Structure

Use one clear primary `<h1>` representing the artist or page.

Use:

- `<h1>` for the primary page heading
- `<h2>` for major page sections
- `<h3>` for subsections when necessary

Do not skip heading levels unnecessarily.

The heading hierarchy should represent the actual content structure rather
than being selected only for visual appearance.

Use CSS to control visual size.

---

# HTML Quality

HTML must be:

- Valid
- Properly nested
- Properly closed
- Well formatted
- Easy to understand

Avoid:

- Duplicate IDs
- Empty headings
- Invalid nesting
- Excessive wrapper elements
- Unnecessary ARIA attributes

---

# CSS and Layout

All styling must be stored in:

`styles.css`

The HTML document must correctly link to this stylesheet.

Use Flexbox as a primary layout method where appropriate.

CSS Grid may be used for localized layouts if it provides a clear benefit.

Do not use:

- `float`
- `display: inline-block`

as the primary page layout technique.

CSS should be:

- Readable
- Organized
- Maintainable
- Non-redundant
- DRY where reasonable

Use meaningful class and ID names.

---

# Responsive Design

The website should work well on:

- Desktop
- Laptop
- Tablet
- Mobile

Avoid fixed-width layouts that cause horizontal scrolling.

Images should scale responsively.

Example:

```css
img {
  max-width: 100%;
  height: auto;
}
```

Typography and spacing should remain readable on smaller screens.

---

# CSS-Only Interactivity

Although JavaScript is not allowed, the website should still feel
interactive.

Appropriate interactions include:

- Navigation anchor links
- Calls to action
- Show links
- Hover states
- Keyboard focus states
- Card hover effects
- Subtle CSS transitions
- Subtle CSS transforms
- Visual feedback for interactive elements

Examples may include:

- Buttons changing appearance on hover
- Cards lifting slightly on hover
- Navigation links changing style on hover and focus
- Links receiving visible keyboard focus

Do not create JavaScript-dependent features such as:

- Carousels
- Modal windows
- Custom tabs
- Custom accordions
- Complex dropdown menus

All functionality must remain usable without JavaScript.

---

# Motion Accessibility

If animations or transitions are used, keep them subtle.

Do not use excessive flashing or distracting movement.

Respect reduced-motion preferences.

Consider:

```css
@media (prefers-reduced-motion: reduce) {
  * {
    scroll-behavior: auto;
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
  }
}
```

Essential information must not depend on animation.

---

# Images and Visual Content

Use high-quality stock imagery that supports the artist's visual identity.

Suitable sources include:

- Unsplash
- Pexels
- Pixabay

Potential imagery may include:

- Artist portraits
- Live performances
- Concert stages
- Music studios
- Instruments
- Audiences
- Performance venues
- Atmospheric artistic photography

Images should feel visually consistent with the site's color palette and
overall style.

Whenever practical:

- Download images locally.
- Store them under `assets/images/`.
- Optimize them before deployment.
- Use modern formats such as WebP or AVIF.
- Avoid excessively large files.
- Use only appropriately licensed images.

---

# Image Accessibility

All meaningful images must include useful `alt` text.

Good example:

```html
alt="Singer performing on stage beneath warm concert lighting"
```

Avoid:

```html
alt="image"
```

or:

```html
alt="photo.jpg"
```

For purely decorative images, use:

```html
alt=""
```

Do not add an ARIA label when appropriate alt text already provides the
image's accessible description.

Important information must never exist only inside an image.

---

# Accessibility Requirements

Accessibility is a core project requirement.

Follow the WCAG POUR principles:

- Perceivable
- Operable
- Understandable
- Robust

Semantic HTML should always be preferred before ARIA.

---

## Perceivable

The page should:

- Provide text alternatives for meaningful images.
- Maintain sufficient color contrast.
- Use readable typography.
- Remain understandable when zoomed.
- Avoid placing important information only inside images.
- Avoid relying on color alone to communicate meaning.

---

## Operable

Users should be able to navigate the website with both a mouse and
keyboard.

Requirements:

- All links must be keyboard accessible.
- Navigation links must be keyboard reachable.
- Visible keyboard focus indicators must be preserved.
- Do not create functionality that works only on hover.
- Prefer native interactive elements.

Include or strongly consider a:

`Skip to main content`

link so keyboard and screen-reader users can bypass repeated navigation.

---

## Understandable

Use:

- Clear headings
- Descriptive navigation
- Meaningful link text
- Predictable page structure
- Clear language

Avoid vague link text such as:

- "Click here"
- "More"
- "Read this"

Prefer:

`View upcoming shows`

or:

`View tickets`

---

## Robust

Use:

- Valid HTML
- Semantic HTML
- Standard HTML and CSS
- Native elements whenever possible

Avoid proprietary or non-standard accessibility implementations.

---

# ARIA Requirements

ARIA should supplement semantic HTML, not replace it.

Follow these rules:

1. Use semantic HTML first.
2. Do not override native semantics unnecessarily.
3. ARIA does not automatically provide keyboard behavior.
4. Never use `aria-hidden="true"` on a keyboard-focusable element.
5. Interactive elements must have an accessible name.

Prefer:

```html
<button>
```

instead of:

```html
<div role="button">
```

A link such as:

```html
<a href="#career">Career</a>
```

already has an accessible name and does not need:

```html
aria-label="Career"
```

Do not add redundant ARIA solely to appear more accessible.

---

# Accessibility Labels

The assignment specifically requires that people with visual impairments
and screen-reader users be able to identify important elements.

Use accessible labels where they provide useful additional context.

For example:

```html
<nav aria-label="Primary navigation">
```

may be useful if multiple navigation landmarks exist.

Icon-only links must have an accessible name.

Example:

```html
<a href="..." aria-label="Visit the artist's Instagram">
```

Visible descriptive text and semantic HTML should remain the primary
accessibility strategy.

---

# Keyboard Focus

Interactive elements must have visible focus indicators.

Do not remove outlines unless they are replaced with an equally visible
focus style.

Use `:focus-visible` where appropriate.

Example:

```css
a:focus-visible {
  outline: 3px solid var(--accent);
  outline-offset: 4px;
}
```

Adjust colors as necessary to maintain sufficient contrast.

---

# SEO Requirements

Search-engine indexing is a core assignment requirement.

The document `<head>` should include:

- UTF-8 character encoding
- Responsive viewport metadata
- Descriptive page title
- Meta description

Declare the document language:

```html
<html lang="en">
```

The visible HTML should clearly communicate:

- Artist name
- Artist profession or type
- Biography
- Career information
- Creative work
- Upcoming performances

Important searchable content must exist as readable HTML text rather than
only in images or decorative graphics.

Use descriptive headings and descriptive anchor text.

---

# SEO Integrity

Do not:

- Keyword stuff
- Hide SEO text
- Create misleading metadata
- Add false structured data
- Make fake claims solely for search ranking

SEO should improve the clarity and discoverability of content for human
visitors as well as search engines.

---

# Schema.org Structured Data

Include appropriate Schema.org structured data.

Choose the type that most accurately represents the artist.

Possible types include:

- `Person`
- `MusicGroup`
- `PerformingGroup`

Relevant properties may include:

- `name`
- `description`
- `url`
- `image`
- `jobTitle`
- `sameAs`

Structured data must accurately match visible page content.

JSON-LD may be used.

Example format:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person"
}
</script>
```

Do not include executable JavaScript in this block.

---

# Upcoming Shows

The Upcoming Shows section should clearly display useful event information.

When available, include:

- Event or show name
- Date
- Time
- City
- Venue
- Ticket or event link

Use semantic HTML where appropriate.

For dates, consider:

```html
<time datetime="2026-11-14">
  November 14, 2026
</time>
```

Show links should use descriptive text such as:

`View tickets`

rather than:

`Click here`

---

# Event Structured Data

Upcoming performances may also use Schema.org Event structured data when
appropriate.

Possible event properties include:

- Event name
- Date
- Time
- Venue
- City
- Event URL

Structured event data must match information visible on the page.

---

# GEO / AI Discoverability

In addition to traditional SEO, structure content so AI-powered search
and answer systems can understand the artist and their work.

Use:

- Clear factual descriptions
- Semantic HTML
- Logical headings
- Structured data
- Schema.org markup
- Clearly identified entities
- Human-readable page content

The site should make it easy to determine:

- Who the artist is
- What they do
- Their career history
- Their creative work
- When and where they perform

GEO is an additional consideration and must not conflict with SEO,
accessibility, performance, or project constraints.

Do not introduce additional technologies solely for GEO.

---

# Performance

The deployed website will be evaluated using PageSpeed Insights.

Target:

- Minimum score: 80
- Preferred score: 90+

Use:

- Optimized images
- Efficient CSS
- Clean HTML
- Minimal external dependencies
- Appropriately sized assets
- Modern image formats where appropriate

Avoid:

- Very large images
- Excessive external fonts
- Unnecessary libraries
- Heavy third-party resources
- Excessive animation

Accessibility and content quality should not be sacrificed solely to
increase performance scores.

---

# Footer

Include an appropriate footer.

Potential footer content may include:

- Artist name
- Copyright information
- Social media links
- Contact information
- Booking information

Icon-only social links should have meaningful accessible names.

---

# Definition of Done

The project is complete when:

## Structure

- [ ] `index.html` exists.
- [ ] `styles.css` exists.
- [ ] HTML and CSS are correctly linked.
- [ ] The site is a single-page experience.
- [ ] Header and navigation are present.
- [ ] Hero section is present.
- [ ] About Me section is present.
- [ ] Career section is present.
- [ ] Upcoming Shows section is present.
- [ ] Footer is present.
- [ ] Navigation links correctly reach their sections.

## Technical Requirements

- [ ] No executable JavaScript is used.
- [ ] No frontend framework is used.
- [ ] No CSS framework is used.
- [ ] No premade template is used.
- [ ] Flexbox is used where appropriate.
- [ ] Major sections use approximately one viewport height where appropriate.

## Design

- [ ] Realtime Colors palette is implemented using CSS variables.
- [ ] Color usage is consistent.
- [ ] Text and backgrounds have sufficient contrast.
- [ ] The site is responsive.
- [ ] The design feels polished and intentional.
- [ ] CSS-only interactions provide appropriate visual feedback.

## Semantic HTML

- [ ] Semantic landmarks are used correctly.
- [ ] There is one meaningful `<h1>`.
- [ ] Heading hierarchy is logical.
- [ ] HTML is valid and properly nested.
- [ ] Generic `<div>` elements are not used where better semantic elements exist.

## Accessibility

- [ ] POUR principles are followed.
- [ ] Semantic HTML is preferred before ARIA.
- [ ] ARIA is used only where necessary.
- [ ] Accessible labels are provided when needed.
- [ ] Redundant ARIA is avoided.
- [ ] Meaningful images have useful alt text.
- [ ] Decorative images use empty alt text.
- [ ] Keyboard navigation works correctly.
- [ ] Interactive elements have visible focus states.
- [ ] Hover interactions have keyboard-focus equivalents.
- [ ] Color is not the only way important information is communicated.
- [ ] Reduced-motion preferences are respected where appropriate.
- [ ] A skip-to-content link is included or considered.

## SEO and Structured Data

- [ ] Document language is declared.
- [ ] Page title is descriptive.
- [ ] Meta description is present.
- [ ] Searchable artist information exists as HTML text.
- [ ] Descriptive anchor text is used.
- [ ] Appropriate Schema.org structured data is included.
- [ ] Structured data matches visible content.
- [ ] Event structured data is used when appropriate.
- [ ] SEO practices are accurate and non-misleading.

## Images and Performance

- [ ] Images are appropriately licensed.
- [ ] Images are relevant to the artist.
- [ ] Images are stored locally when practical.
- [ ] Images are optimized.
- [ ] Unnecessary dependencies are avoided.
- [ ] PageSpeed Insights score is at least 80.
- [ ] A score of 90+ is preferred.

---

# Agent Implementation Instructions

Before changing the project:

1. Read this entire `product_context.md`.
2. Review the existing repository files.
3. Briefly describe the planned implementation.
4. Explain the intended semantic HTML structure.
5. Explain the accessibility approach.
6. Explain how the selected color palette will be used.
7. Explain the SEO and Schema.org strategy.
8. Explain how the site will feel interactive without JavaScript.

When implementing:

- Use semantic HTML before ARIA.
- Keep HTML and CSS in separate files.
- Do not introduce executable JavaScript.
- Do not introduce frameworks or premade templates.
- Use the specified Realtime Colors palette.
- Keep accessibility, SEO, performance, and maintainability as priorities.
- Avoid unnecessary complexity.
- Prefer simple, standards-based solutions.
- Do not invent requirements that conflict with this document.
