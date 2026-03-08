# RRUGA STUDIOS — Shopify Theme (Dawn)

## Store Info
- **Brand:** RRUGA STUDIOS
- **Store URL:** saharasandtest.myshopify.com
- **Base Theme:** Dawn

## Brand Identity
- **Industry:** Fashion / Clothing
- **Aesthetic:** Minimal, Raw, Brutalist, Streetwear
- **Design Inspiration:** No Fear (nofear.virus.london) — extremely stripped back, no decoration
- **Background Color:** #FFFFFF (pure white)
- **Primary Text Color:** #000000 (Black)
- **Button Background:** #000000
- **Button Text:** #FFFFFF
- **Font:** Space Mono (provided as SpaceMono-Regular.woff2)
- **Font Fallback:** monospace

## Font Setup
- Font file: `assets/SpaceMono-Regular.woff2`
- Always use this CSS to load the font:
```css
@font-face {
  font-family: 'Space Mono';
  src: url('{{ 'SpaceMono-Regular.woff2' | asset_url }}') format('woff2');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}

*, *::before, *::after {
  font-family: 'Space Mono', monospace !important;
  font-size: 12px !important;
  font-weight: 400 !important;
}
```
- ALL text across the entire website must be 12px — no exceptions
- This includes headings, titles, body text, buttons, labels, nav links, prices, everything
- Never use any other font size — not for titles, not for headings, not for anything
- All text UPPERCASE everywhere

## Color Palette
- **Page background:** #FFFFFF (pure white)
- **All section backgrounds:** #FFFFFF
- **Text:** #000000
- **Borders:** 1px solid #000000
- **Buttons:** #000000 background, #FFFFFF text

## Design Style
Inspired by No Fear (nofear.virus.london). Key principles:
- Extremely raw and minimal — nothing decorative
- Pure white background everywhere
- Everything UPPERCASE
- No rounded corners — border-radius: 0 always
- No shadows, no gradients, no hover animations
- 12px font size for ALL text — uniform across entire site
- Products are the focus — clean grid, maximum image space
- Thin 1px black borders used for structure
- No padding waste — content is tight and purposeful

## Header / Navbar
- Minimal single line
- Left: brand name "RRUGA STUDIOS" + navigation links (SHOP, INFO) — each in a box with 1px black border
- Right: CART 0 — in a box with 1px black border
- White background
- 1px solid #000000 bottom border on navbar
- No shadows, no hover effects except cursor change
- 12px font size, UPPERCASE, Space Mono
- Navigation items have visible 1px border boxes around them like buttons

## Collection / Shop Page (Product Grid)
- 4 columns on desktop, 2 on mobile
- Each product card has 1px solid #000000 border
- Borders between cards COLLAPSE and share — use negative margins so borders connect:
```css
.product-card {
  border: 1px solid #000000;
  margin: -1px 0 0 -1px;
}
.product-grid {
  border-top: 1px solid #000000;
  border-left: 1px solid #000000;
}
```
- Product image fills full card width — square or portrait ratio
- White background on cards
- Below image: product name UPPERCASE, 12px
- Price below name, 12px
- No hover effects
- No card shadows
- No border-radius

## Product Page
- Split layout: left 50% = product images, right 50% = product info
- Full height minus navbar: height: calc(100vh - navbar-height)
- Background #FFFFFF throughout

**LEFT SIDE:**
- All product images stacked vertically, scrollable
- Images full width of left panel
- No borders around images
- White background

**RIGHT SIDE (sticky — stays fixed while left scrolls):**
- position: sticky; top: 0; height: calc(100vh - navbar-height)
- Separated from left by 1px solid #000000 vertical line
- Display flex, flex-direction: column

**RIGHT SIDE LAYOUT:**

TOP SECTION (flex: 1, takes all available space):
- Product title UPPERCASE, 12px, top of panel with padding
- Large empty whitespace
- Centered vertically in remaining space:
  - "product details -" label lowercase, centered, 12px
  - Description lines each starting with "- ", centered, 12px
  - "sizing chart +" link centered below, 12px

BOTTOM SECTION (pinned to bottom with 1px top border):
- Row 1: SIZE label + dropdown on LEFT, QUANTITY label + minus/number/plus on RIGHT — side by side with space-between
- 1px horizontal divider line
- Row 2: Price centered, 12px, UPPERCASE
- Row 3: Add to cart — full width, #000000 background, #FFFFFF UPPERCASE text, 12px, border-radius: 0

## Cart Page
- White background
- Each item separated by 1px black divider
- Product image left, details right
- Product name UPPERCASE, 12px
- Quantity controls: - / number / +
- Price right aligned, 12px
- TOTAL UPPERCASE, 12px
- CHECKOUT button full width, black background, white text, 12px

## Info / Static Pages
- Pure white background
- All text UPPERCASE, Space Mono, 12px
- No decoration — just raw text layout
- Generous line height for readability

## Typography Rules
- **Font:** Space Mono everywhere
- **Font size:** 12px for EVERYTHING — no exceptions, no overrides
- **Text transform:** UPPERCASE for everything
- **Letter spacing:** 0.05em to 0.1em
- **Line height:** 1.6
- **Font weight:** 400 regular only — never bold

## Layout Rules
- border-radius: 0 everywhere — no exceptions
- No box-shadows
- No gradients
- No animations or transitions
- Max content width: 1400px centered
- Mobile: 2 column grid, stacked product page

## File Structure
- `sections/` → theme sections
- `assets/` → CSS, JS, SpaceMono-Regular.woff2
- `snippets/` → reusable components
- `templates/` → page templates
- `config/` → theme settings

## Important Rules
- Always mobile responsive
- Never break Shopify functionality — design only
- Always UPPERCASE for all text
- Always 12px font size — no exceptions anywhere on the site
- Always #FFFFFF background
- Always Space Mono font
- Always border-radius: 0
- Add SpaceMono-Regular.woff2 to assets/ before starting
- When editing CSS add to existing stylesheet — never duplicate rules

## Git Workflow
- Branch: main → connected to Shopify via GitHub
- Every git push to main auto-deploys to live store
- Always commit with clear message describing changes
