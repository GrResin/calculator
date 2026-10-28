# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Three audiences, weighted equally (confirmed 2026-10-28):

- **Customers on a phone**: arrive from a Meta ad, the Projects WhatsApp bot or a shared link, enter an area and see how much material a flooring system needs and what it costs, then order on WhatsApp.
- **Showroom visitors on the Labeib kiosk**: the page runs inside Labeib's iframe on a touchscreen; WhatsApp can't open there, so ordering goes through a QR code scanned with the visitor's phone.
- **Graffiti Resin's sales team** (`/sales/`, `?mode=sales`): edit consumption rates within the approved range, remove materials, and send the quote (with a link that reopens the same calculation) to any WhatsApp contact.

## Product Purpose

A materials calculator for Graffiti Resin's resin, epoxy, PU and cementitious flooring and waterproofing systems, plus single products. For an area (and layers or thickness where the system has them) it shows each material's consumption rate, the quantity needed, the packs to buy, pack prices and the VAT-inclusive total, then hands the order to the Projects WhatsApp number. Success: a customer trusts the numbers enough to order, and the sales team quotes faster than by hand.

## Positioning

Numbers come straight from Graffiti Resin's own consumption sheet, approved by its technical team, and its monthly price list. It is the company's own figures, not a generic coverage estimator.

## Operating Context

- Live at `https://calc.grresin.com` (public repo `GrResin/calculator`, deployed by `git pull` on the VPS). `/<system-id>/` folders redirect to `?system=<id>`.
- Arabic RTL by default, English toggle; customer messages and quotes are in the chosen language.
- Embedded in the Labeib kiosk iframe (`EMBEDDED` path: QR dialog instead of WhatsApp).
- Shared links restore a calculation: `area`, `n` (layers/thickness), `color`, `r` (edited rates), `x` (removed materials), `lang`, `mode`.
- Prices change monthly and are copied by hand from the KB price sheet.

## Capabilities and Constraints

- Single static `index.html` (inline CSS/JS) plus `qrcodejs`; no build step, no framework.
- Rates may be ranges (min–max); customer quantities use the max; sales may type a rate inside the range.
- Some products have no price or pack size in the price list: quantity only, "on request".
- Prices are stored in USD internally (`sar()`), shown in SAR, with an optional USD line.
- Estimates only; the final technical offer decides.

## Brand Commitments

None binding visually (confirmed 2026-10-28): colour, logo treatment and type may all change. The company name is Graffiti Resin (جرافيتي ريزن).

## Evidence on Hand

- Data: systems and products in `index.html` (consumption sheet + price list).
- No product photography for now (confirmed 2026-10-28); do not use stock photos of floors.
- No testimonials, case studies or certifications are available; do not invent any.

## Product Principles

1. The numbers are the product: every figure must be legible, traceable to its rate, and never hidden behind decoration.
2. Works the same for a phone, a showroom touchscreen and a salesperson's laptop.
3. Arabic-first: RTL layout and Arabic typography are the primary case, English is the mirror.
4. Ordering is one tap (or one scan) away from the total.

## Accessibility & Inclusion

Touchscreen kiosk use: large tap targets and readable type from standing distance. Bilingual Arabic/English.
