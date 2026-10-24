# product_data.md

Sample data for **Zephyr**, a toy drone and camera store (our own product idea for the 5-view e-commerce prototype). **Everything here is fictional.**

The project is **HTML + Tailwind only** (no JavaScript, no React), so this file is the single source of truth that we copy into the HTML pages by hand. Keep names, codes, prices, and image filenames exactly as written so every page stays consistent.

## Where each view uses this data

| View | Uses |
|---|---|
| Home | Site info, Hero campaigns, products with `collection: new-arrivals` and `collection: best-sellers`, footer info |
| Catalog | All 20 products (4 columns x 5 rows), filters by `category` and `sizes` |
| Product view | One product: `name`, `code`, `sizes`, `price`, `materials`, `recommended_use`, `description` |
| Cart | The 3 sample cart items and tax rate below |
| Checkout | The 3 form steps below |

---

## 1. Site info (navbar, footer, Schema.org `Organization`)

- brand: Zephyr
- tagline: Capture the sky.
- url: https://zephyr.example
- logo: logo.svg
- email: hello@zephyr.example
- phone: +1 555-0100
- address: 123 Sample Street, Springfield, USA
- currency: USD
- tax_rate: 8%

### Navbar
- Logo (links to home)
- Search bar placeholder: `Search drones, cameras, accessories`
- Account menu: Sign in / Create account / My orders
- Cart icon (links to the cart)

### Footer
- **Categories:** Camera Drones, Handheld, Power, Accessories
- **Legal:** Terms and conditions, Privacy policy, About the brand
- **Contact:** hello@zephyr.example, +1 555-0100, 123 Sample Street, Springfield, USA

---

## 2. Hero campaigns (home page)

### Hero 1
- eyebrow: New
- headline: Zephyr Air
- tagline: Chase the View
- product: zephyr-air
- image: hero-zephyr-air.jpg
- buttons: Learn More (product page) / Buy Now (cart)

### Hero 2
- eyebrow: Creator Season
- headline: Pack It, Take It
- tagline: Free Sky Case with any drone combo
- product: sky-case
- image: hero-creator-season.jpg
- buttons: Learn More (catalog)

---

## 3. Product fields

| Field | Meaning | Example |
|---|---|---|
| `id` | unique slug, also the image filename | `zephyr-mini` |
| `code` | product reference / SKU shown on the product page | `ZPH-DR-003` |
| `name` | product name | `Zephyr Mini` |
| `category` | one of the 4 footer categories | `Camera Drones` |
| `tagline` | 2-4 words | `Light as Air` |
| `summary` | one line shown on cards | |
| `price` | USD number for the default (first listed) size | `479` |
| `sizes` | options for the size selector and the size filter | `S, M, L` |
| `collection` | `new-arrivals`, `best-sellers`, or `none` (drives the home sections and card badges) | |
| `image` | file in `/images/products/` | `zephyr-mini.jpg` |
| `specs` | 3 short facts | |
| `materials` | shown in the description section | |
| `recommended_use` | when and where to use it (description section) | |
| `description` | 1-2 sentences | |
| `availability` | `InStock` (maps to Schema.org) | `InStock` |

### Size guide

- **Drones, handheld, power:** S = Standard (device only), M = Combo (extra battery or accessories), L = Pro Combo (adds case and extras).
- **Accessories with sizes:** S / M / L = physical fit (S fits Mini, M fits Air, L fits Pro).
- **One Size:** fixed, no choice.

The size does not change the price in this static prototype.

---

## 4. Products (20)

## Camera Drones

### Zephyr Neo
- id: zephyr-neo
- code: ZPH-DR-001
- name: Zephyr Neo
- category: Camera Drones
- tagline: Fly Your Moment
- summary: Palm-sized selfie drone, no controller needed
- price: 199
- sizes: S, M
- collection: new-arrivals
- image: zephyr-neo.jpg
- specs: 18 min flight / 1080p 30fps / 135 g
- materials: Recycled ABS shell, carbon-fiber-blend propellers
- recommended_use: First flights, selfies, backyard and indoor use
- description: A tiny drone that launches from your palm and follows you around. A friendly first step into flying.
- availability: InStock

### Zephyr Flip
- id: zephyr-flip
- code: ZPH-DR-002
- name: Zephyr Flip
- category: Camera Drones
- tagline: Open New Possibilities
- summary: Foldable vlog drone with propeller guards
- price: 439
- sizes: S, M
- collection: none
- image: zephyr-flip.jpg
- specs: 31 min flight / 4K 30fps / 249 g
- materials: Polycarbonate body, nylon propeller guards
- recommended_use: Vlogging, family trips, close-range filming
- description: Folds flat for the bag and flies safely around people thanks to its built-in guards.
- availability: InStock

### Zephyr Mini
- id: zephyr-mini
- code: ZPH-DR-003
- name: Zephyr Mini
- category: Camera Drones
- tagline: Light as Air
- summary: Under-250 g foldable drone for beginners
- price: 479
- sizes: S, M, L
- collection: best-sellers
- image: zephyr-mini.jpg
- specs: 34 min flight / 4K 30fps / 249 g
- materials: Magnesium-alloy frame, polycarbonate shell
- recommended_use: Travel, hiking, beginner aerial photography
- description: Our most popular drone. Light enough to carry anywhere and simple enough to fly on day one.
- availability: InStock

### Zephyr Air
- id: zephyr-air
- code: ZPH-DR-004
- name: Zephyr Air
- category: Camera Drones
- tagline: Chase the View
- summary: Dual-camera drone for travel photography
- price: 999
- sizes: S, M, L
- collection: new-arrivals
- image: zephyr-air.jpg
- specs: 45 min flight / 4K 60fps / 720 g
- materials: Carbon-fiber arms, magnesium-alloy frame
- recommended_use: Landscape photography, travel films, sunset shoots
- description: Two cameras and a long flight time make this the go-to drone for capturing big views.
- availability: InStock

### Zephyr Pro
- id: zephyr-pro
- code: ZPH-DR-005
- name: Zephyr Pro
- category: Camera Drones
- tagline: Inspiration in Focus
- summary: Triple-lens camera drone for creators
- price: 2199
- sizes: M, L
- collection: none
- image: zephyr-pro.jpg
- specs: 43 min flight / 5.1K 50fps / 958 g
- materials: Carbon-fiber composite body, magnesium-alloy gimbal
- recommended_use: Commercial shoots, cinematic projects, real estate
- description: Three lenses, a large sensor, and pro-grade stabilization for work that has to look perfect.
- availability: InStock

---

## Handheld

### Pocket Cam 3
- id: pocket-cam-3
- code: ZPH-HH-001
- name: Pocket Cam 3
- category: Handheld
- tagline: For Moving Moments
- summary: 1-inch pocket gimbal camera
- price: 519
- sizes: S, M
- collection: best-sellers
- image: pocket-cam-3.jpg
- specs: 1-inch sensor / 4K 120fps / 179 g
- materials: Aluminum body, glass lens
- recommended_use: Vlogs, street video, travel diaries
- description: A camera and a gimbal in one tiny body. Smooth footage straight out of your pocket.
- availability: InStock

### Action Cam 6
- id: action-cam-6
- code: ZPH-HH-002
- name: Action Cam 6
- category: Handheld
- tagline: Square Up, Nail the Move
- summary: Waterproof flagship action camera
- price: 379
- sizes: S, M, L
- collection: new-arrivals
- image: action-cam-6.jpg
- specs: 20 m waterproof / 4K 120fps / 145 g
- materials: Polycarbonate shell, tempered-glass lens, silicone seals
- recommended_use: Biking, surfing, skiing, any fast sport
- description: Built to get wet, dropped, and frozen, and still film steady, sharp footage.
- availability: InStock

### Phone Gimbal 8
- id: phone-gimbal-8
- code: ZPH-HH-003
- name: Phone Gimbal 8
- category: Handheld
- tagline: In Tune With Every Move
- summary: Intelligent tracking phone gimbal
- price: 159
- sizes: S, M
- collection: best-sellers
- image: phone-gimbal-8.jpg
- specs: 3-axis stabilization / 10 hr battery / 368 g
- materials: Nylon-reinforced plastic, aluminum folding arm
- recommended_use: Social videos, interviews, walking shots
- description: Keeps your phone footage smooth and your subject centered, even when you are walking.
- availability: InStock

### Stabilizer S5
- id: stabilizer-s5
- code: ZPH-HH-004
- name: Stabilizer S5
- category: Handheld
- tagline: Lead the Scene
- summary: Lightweight stabilizer for mirrorless cameras
- price: 749
- sizes: M, L
- collection: none
- image: stabilizer-s5.jpg
- specs: 3 kg payload / 12 hr battery / 1.2 kg
- materials: Magnesium-alloy frame, carbon-fiber arms
- recommended_use: Film sets, weddings, event coverage
- description: A pro stabilizer light enough to hold for a full shoot day.
- availability: InStock

### Orbit 360
- id: orbit-360
- code: ZPH-HH-005
- name: Orbit 360
- category: Handheld
- tagline: See It All
- summary: 8K 360-degree camera
- price: 449
- sizes: S, M
- collection: new-arrivals
- image: orbit-360.jpg
- specs: 8K 360 video / 2 lenses / 183 g
- materials: Polycarbonate body, tempered-glass lenses
- recommended_use: Virtual tours, travel recaps, creative reframing
- description: Film everything around you, then choose the best angle afterward.
- availability: InStock

---

## Power

### PowerBox 300
- id: powerbox-300
- code: ZPH-PW-001
- name: PowerBox 300
- category: Power
- tagline: Small Size, Big Power
- summary: Compact power station for day trips
- price: 299
- sizes: S, M
- collection: new-arrivals
- image: powerbox-300.jpg
- specs: 256 Wh / 300 W output / 4 kg
- materials: Flame-retardant ABS shell, aluminum handle
- recommended_use: Day trips, drone charging, light camping
- description: Charges a drone, a camera, and your phone several times over, and still fits in a backpack.
- availability: InStock

### PowerBox 600
- id: powerbox-600
- code: ZPH-PW-002
- name: PowerBox 600
- category: Power
- tagline: Power Anywhere
- summary: Portable power station for camping and shoots
- price: 499
- sizes: S, M, L
- collection: none
- image: powerbox-600.jpg
- specs: 512 Wh / 600 W output / 7 kg
- materials: Flame-retardant ABS shell, reinforced steel corners
- recommended_use: Camping, outdoor shoots, home backup
- description: The all-rounder: enough power for a weekend away or a full day of filming.
- availability: InStock

### PowerBox 1000
- id: powerbox-1000
- code: ZPH-PW-003
- name: PowerBox 1000
- category: Power
- tagline: Built to Last
- summary: High-capacity station with fast recharge
- price: 899
- sizes: M, L
- collection: best-sellers
- image: powerbox-1000.jpg
- specs: 1024 Wh / 1000 W output / 11 kg
- materials: Flame-retardant ABS shell, steel frame
- recommended_use: Long shoots, off-grid trips, home backup
- description: Big capacity and fast recharging for projects that run all day.
- availability: InStock

### SolarFold 100
- id: solarfold-100
- code: ZPH-PW-004
- name: SolarFold 100
- category: Power
- tagline: Charge by Sunlight
- summary: Foldable 100 W solar panel
- price: 199
- sizes: S, M
- collection: none
- image: solarfold-100.jpg
- specs: 100 W output / IP65 rated / 4.5 kg
- materials: Monocrystalline silicon cells, ETFE surface, nylon carry cover
- recommended_use: Camping, remote shoots, recharging power stations
- description: Unfolds in seconds and keeps your PowerBox topped up wherever the sun is.
- availability: InStock

### Charge Hub 3
- id: charge-hub-3
- code: ZPH-PW-005
- name: Charge Hub 3
- category: Power
- tagline: Charge Them All
- summary: Three-battery fast charging hub
- price: 79
- sizes: One Size
- collection: none
- image: charge-hub-3.jpg
- specs: 3 batteries / 65 W / 210 g
- materials: Fire-resistant polycarbonate, aluminum contacts
- recommended_use: Charging flight batteries between shoots
- description: Charges three batteries in order so you always have a full one ready.
- availability: InStock

---

## Accessories

### Sky Case
- id: sky-case
- code: ZPH-AC-001
- name: Sky Case
- category: Accessories
- tagline: Pack It, Take It
- summary: Water-resistant carry case for drones
- price: 59
- sizes: S, M, L
- collection: best-sellers
- image: sky-case.jpg
- specs: Water-resistant / padded dividers / 600 g
- materials: Recycled nylon exterior, EVA foam interior
- recommended_use: Travel, hiking, carry-on luggage
- description: Protects your drone, controller, and batteries in one padded case.
- availability: InStock

### Prop Set
- id: prop-set
- code: ZPH-AC-002
- name: Prop Set
- category: Accessories
- tagline: Fresh Blades
- summary: Replacement propeller set
- price: 19
- sizes: S, M, L
- collection: best-sellers
- image: prop-set.jpg
- specs: 4 propellers / low-noise design / 12 g
- materials: Glass-fiber reinforced nylon
- recommended_use: Replacing worn or damaged propellers
- description: Keep spare blades in your case so a minor bump never ends the day.
- availability: InStock

### ND Filter Kit
- id: nd-filter-kit
- code: ZPH-AC-003
- name: ND Filter Kit
- category: Accessories
- tagline: Control the Light
- summary: ND filter set for smoother video
- price: 49
- sizes: S, M, L
- collection: none
- image: nd-filter-kit.jpg
- specs: ND8, ND16, ND32 / snap-on / 20 g
- materials: Optical glass, aluminum frame
- recommended_use: Bright daylight video, long exposures
- description: Three filters that tame bright light for cinematic motion blur.
- availability: InStock

### Clip Mic 3
- id: clip-mic-3
- code: ZPH-AC-004
- name: Clip Mic 3
- category: Accessories
- tagline: Clear Voice
- summary: Wireless clip-on microphone
- price: 99
- sizes: One Size
- collection: new-arrivals
- image: clip-mic-3.jpg
- specs: 250 m range / 8 hr battery / 15 g
- materials: Aluminum clip, soft-touch plastic body
- recommended_use: Interviews, vlogs, tutorials
- description: Crisp, noise-reduced audio that clips to your shirt and connects in seconds.
- availability: InStock

### Memory Card 128
- id: memory-card-128
- code: ZPH-AC-005
- name: Memory Card 128
- category: Accessories
- tagline: Never Run Out
- summary: 128 GB high-speed memory card
- price: 25
- sizes: One Size
- collection: none
- image: memory-card-128.jpg
- specs: 128 GB / V30 / 160 MB/s
- materials: Plastic casing with sealed gold contacts
- recommended_use: 4K video recording, burst photography
- description: Fast enough for 4K video, with room for a full day of footage.
- availability: InStock

---

## 5. Cart sample (3 items)

| Product | Size | Unit price | Qty | Line total |
|---|---|---|---|---|
| Zephyr Mini (`zephyr-mini`) | M | $479.00 | 1 | $479.00 |
| Action Cam 6 (`action-cam-6`) | S | $379.00 | 2 | $758.00 |
| Prop Set (`prop-set`) | S | $19.00 | 3 | $57.00 |

| Summary | Amount |
|---|---|
| Subtotal | $1,294.00 |
| Tax (8%) | $103.52 |
| **Total** | **$1,397.52** |

Button: **Purchase** (links to checkout).

---

## 6. Checkout steps

Use real `<form>`, `<fieldset>`, `<legend>`, and `<label>` elements. **Never type real personal or card data in the prototype.** Use placeholders only.

**Step 1: Personal details**
- Full name (`Alex Rivera`)
- Email (`alex@example.com`)
- Phone (`555-0100`)

**Step 2: Shipping address**
- Address line 1 (`123 Sample Street`)
- Address line 2, optional (`Apt 4`)
- City (`Springfield`)
- State / Region (`VA`)
- ZIP / Postal code (`00000`)
- Country (`United States`)

**Step 3: Card payment**
- Name on card (`Alex Rivera`)
- Card number (`0000 0000 0000 0000`)
- Expiry (`MM/YY`)
- CVC (`123`)

Order summary sidebar: reuse the cart totals above.

---

## 7. Schema.org mapping

| Our field | Schema.org property |
|---|---|
| `name` | `Product.name` |
| `code` | `Product.sku` |
| `description` | `Product.description` |
| `image` | `Product.image` |
| `category` | `Product.category` |
| `materials` | `Product.material` |
| brand (`Zephyr`) | `Product.brand` (`Brand`) |
| `price` + `currency` | `Product.offers.price` + `priceCurrency` |
| `availability` | `Product.offers.availability` (`https://schema.org/InStock`) |

Home page: add `Organization` JSON-LD using the Site info above (`name`, `url`, `logo`, `email`, `telephone`, `address`).
Product page: add `Product` JSON-LD using the mapping above.
Do not add `aggregateRating` or `review` unless the page shows real reviews.