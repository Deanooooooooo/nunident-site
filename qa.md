# Нунидент — QA

QA date: 2026-05-29. Local QA server: `http://127.0.0.1:8765`.

## Gate 1 — source/fact audit: PASS
- Name/profession/source row: Нунидент, зъболекар, row 25 source provided by Dean.
- NAP: Google Maps place `ChIJ33qUQsaHqkAR71zYGvNvDx4`; j-stil mirror confirms name/address/phone.
- Address: ул. „Самоковско шосе“ 1, 1138 кв. Горубляне, София — Google Maps + j-stil.
- Phone: +359 878 799 899 — Google Maps + j-stil.
- Website: Google Maps shows “Добавяне на уебсайт”; no official standalone domain found in Brave searches.
- Socials: no verified Facebook/Instagram for this business. Search result for NuridentBulgaria rejected as different clinic.
- Hours: Google Maps expanded hours — Mon–Fri 09:00–18:00; Sat/Sun closed.
- Testimonials: Google Maps reviews manually inspected and source text captured in `research/maps-reviews-text.txt` / `research/hours-expanded-text.txt`.
- Images: Google Maps photos recorded in `image-map.md`.
- No invented prices, certifications, awards, guarantees, review counts, or unsupported medical claims.

## Gate 2 — visual-result image audit: PASS / not applicable
Dentist/clinic site, not a visual-result salon/beauty lead. Clinical before/after photo was found but rejected as too graphic for homepage.

## Gate 3 — testimonial audit: PASS
- Google Maps reviews manually inspected via Playwright.
- Site uses real reviewer names and exact/excerpted original-language visible text from Google reviews: Викторя Димитрова, Vania Nikolova, Iva Nikolova.
- No anonymous/fake/rating-only testimonial cards.
- No public review count is displayed.

## Gate 4 — copy audit: PASS
- Bulgarian copy reviewed for customer-facing language.
- No internal audit/source mechanics in visitor copy.
- No TODO/Lorem/placeholder copy.
- No numbered service/feature boxes.

## Gate 5 — links/schema/SEO-head audit: PASS
- Phone links: `tel:+359878799899`.
- Google Maps navigation link includes business/address/place_id.
- SEO head present: title, meta description, robots, canonical, OG tags, twitter card, absolute OG image.
- Exactly one H1.
- JSON-LD Dentist schema includes name, URL, image, phone, address, opening hours, area served, sameAs.

## Gate 6 — image/layout audit: PASS
- Images load locally; QA JSON in `artifacts/nunident-qa/desktop.json` and `mobile.json` confirms natural dimensions.
- Hero uses clean real clinic interior. Gallery uses different equipment and exterior/location photos.
- Rejected graphic before/after image from homepage.
- No duplicate image files used as separate gallery variety.

## Gate 7 — map/local SEO audit: PASS
- Bottom Google Maps/local SEO block is directly above footer.
- Contact/map block has exactly one visible navigation CTA: “Отворете навигация”.
- Embedded Google map iframe is present and loads when scrolled into view. Evidence: `artifacts/nunident-qa/map-section.png`.

## Gate 8 — responsive visual QA: PASS
- Desktop and mobile screenshots created: `artifacts/nunident-qa/desktop.png`, `artifacts/nunident-qa/mobile.png`.
- Sticky mobile call CTA present.
- Footer uses consistent SVG icon buttons for phone/maps.

## Gate 9 — final live QA after deploy: PASS
- Live URL returned HTTP 200 after GitHub Pages build.
- Live HTML contains business name, testimonial phrase “Обслужването беше невероятно”, schema, canonical, OG tags, phone links, and map/contact block.

## 2026-05-30 Facebook hero-image correction
- PASS: Re-opened Nunident Facebook photos page supplied by Dean.
- PASS: Downloaded and vetted public Facebook images.
- PASS: Replaced weak main hero/OG/schema image with verified Facebook clinic photo.
- PASS: Added Facebook logo/profile image only as a secondary visual; rejected generic/tiny assets.
- PASS: No visible duplicate image srcs after correction.
