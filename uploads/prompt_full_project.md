# Belbes Studio — Site Generation Prompt

**Project:** `p_real13`
**Tariff:** landing
**Niche:** creative-agency

This prompt drives Claude Design's Pages generation, **after** the Design System is published. Attached files (paperclip): `composition.json`, `brief.json`, `creative_direction.json`. The DS already encodes typography/colors/components — this prompt focuses on layout grid, sitemap, и per-page content briefs.


---

## Grid Logic

*Component:* `cmp_full_bleed_editorial_pacing@1.0.0`

# Magazine-spread full-bleed hero rhythm

**Axis:** `grid_logic`
**Component ID:** `cmp_full_bleed_editorial_pacing`

## When this component is selected

См. `vector_centroid` (density=0.32 → sparse band) + `niche_affinity`.

## Pattern signals

- `full-bleed-hero` (3×)
- `low-density-editorial` (2×)
- `vertical-sidebar-nav` (1×)
- `asymmetric-vertical-nav` (1×)
- `magazine-pacing-rhythm` (1×)
- `full-bleed-aerial-hero` (1×)
- `3-col-sub-brand-section` (1×)
- `manifest-footer-display` (1×)
- `5-section-low-density` (1×)
- `full-bleed-interior-hero` (1×)

## Grid directives 

**Column structure:**
- Columns: **2**
- Breakpoints: [320, 768, 1024, 1440] (mobile / tablet / laptop / desktop)
- Hero layout: **full-bleed**

**Density profile (`sparse`):**
- Row rhythm: 24px baseline grid
- Gutter: 48px between columns
- Margin: 96px page padding
- Section count target: ~6 sections
- Rhythm: **accelerating**

**Section pacing details:**
- Accelerating — sections shorter as user scrolls deeper (editorial)

## Anti-patterns

- вертикальный sidebar nav требует серьёзного UX-investment; без продуманной реализации сбивает пользователей, ожидающих стандартную топ-навигацию
- tracklist layout works только для venue с реальной music programming; для cafe/restaurant без концепции = неуместно

---

## Sitemap


- **index.html** (landing) — hero + main CTA

- **about.html** (company) — story, team, values

- **products.html** (offering) — services / products list

- **404.html** (error) — graceful 404 with brand voice


---

## Brief Highlights


**Main message:** Mock chain test message


**CTA goal:** request_demo


**Target audience:** V6.2.9 D5.2 mock chain test



---

## Output Format

Generate a complete static multi-page website implementing the Design System и this site brief.

**Required pages:** index.html, about.html, products.html, 404.html.
**Required asset:** `assets/styles.css` (shared CSS with semantic tokens matching the published Design System).

Constraints:
- All HTML must be valid HTML5 with semantic landmarks (`<header>`, `<main>`, `<footer>`, `<nav>`).
- All inter-page links must be relative.
- Do NOT use Tailwind utility classes — write plain CSS only.
- Do NOT use Lorem ipsum — use real content driven by the brief.
- Hero must surface main_message in <30s scan.
