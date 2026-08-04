# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2026-08-02

### Added
- **Astro Core:** Initialized Astro v4.15 (SSG) in the root of the workspace to ensure compatibility with Node.js v22.11.
- **Design Tokens (`src/styles/style-variables.css`):** Integrated standard variables for color themes (Dark Theme by default, Brand Theme with Heritage Cream background) and typography (Sora and Inter fonts). Updated exact brand hex colors (Indigo `#1B2A56`, Warm Amber `#F5A524`, Dark Ink `#0E1424`).
- **Global Styles (`src/styles/style-global.css`):** Formatted global resets, active scroll snapping for viewport-proportional layout, standard responsive button system and custom Glassmorphism panels.
- **Layout Components:**
  - `comp-navbar.astro` with mobile toggle support and native Theme Switcher (Dark vs. Brand/Cream) using CSS variables and local storage persistence. Integrated inline vector brand logo using the official "LN" monogram (adaptable to themes via currentColor).
  - `comp-footer.astro` containing corporate links, social channels and Luis Niño Developer brand messaging.
- **Favicon & Brand Identity:** Created `favicon.svg` using the official avatar-styled "LN" monogram with dark background and warm amber diamond cursor detail. Linked in main entry head.
- **Landing Page Features:**
  - `comp-hero.astro` designed with strong value proposition headings, glow decoration and dual CTA links.
  - `comp-audit-tool.astro` featuring a step-by-step interactive questionnaire (12 key conversion metrics), dynamic conversion health index and client drop-off rate estimator.
  - `comp-audit-form.astro` configured with work email, name, website, and phone (WhatsApp) inputs. Synchronized with hidden fields containing audit results for serverless processing via Web3Forms.
  - `comp-offer-details.astro` detailing Luis' profile, historical storytelling ("Turbo C at 15", Vancouver, "David vs. Goliath"), and 1-on-1 personalized manual video audit benefits.
  - `comp-faq.astro` with accordion styling and native vanilla JS toggle behaviour for frequent questions.
- **Routing Integration:**
  - `page-index.astro` integrating all sections and setting up canonical HTML URLs and SEO metadata.
  - `index.astro` acting as the file-based route gateway component mapping `/`.

### Fixed
- **Light Theme Button Contrast:** Added dynamic color variable `--color-accent-primary-text` to ensure high accessibility contrast of primary call-to-actions in Light/Brand cream theme (reverting invisible text bugs).
- **Study Cases Credibility:** Restructured project portfolio with a verified project showcase (*Maíz del Sol*) and flagged projected industry models with clarification guidelines.
- **Brand Identity & Avatar:** Removed default code glyphs `</>` from personal cards and integrated Luis Niño's real photographic portrait (`asset-luis-avatar.jpg`).
- **Form Friction Reduction:** Remapped phone/WhatsApp fields as optional. Added agenda limitation warnings to set realistic expectations on manual audits.
- **Color Consistency:** Normalized heading highlight text underline values to match warm brand amber `#F5A524` in all color modes.
- **Unified Footer Monogram:** Succeeded in replacing residual code symbols in the footer brand segment with the official unified "LN" monogram SVG.
- **Mobile Menu Interactive Toggle:** Designed and implemented responsive CSS styles for the vertical navbar dropdown (`.nav-mobile-active`) along with smooth state animations for the hamburger icon lines (transforming to X) and auto-closing behaviors upon link selections. Solved legibility overlay bugs by applying a 100% solid theme-based background color (`var(--color-bg-primary)`) and enforcing high-contrast text settings for all links.
- **Smooth FAQ Accordion Animation:** Remapped CSS transitions (`max-height`, `opacity`, and `padding`) combined with dynamic JavaScript calculations (`scrollHeight`) to animate the vertical dropdown opening and closing actions of the accordion items smoothly, eliminating abrupt jumps.
- **Adaptive Branding & Dynamic Favicon:** Built and integrated two distinct brand logo variants conforming to active themes: Orange/Amber background box (`#f5a524`) for dark mode and Deep Blue background box (`#1b2a56`) for light/brand mode. Succeeded in adding JavaScript event triggers to swap browser favicons dynamically (`favicon-dark.svg` and `favicon-brand.svg`) upon theme selections.
- **Viewport Height & Form Overflow:** Solved structural height bugs where the fixed header collided with section titles and form fields overflowed on smaller vertical screens. Replaced clipping layout properties (`overflow: hidden`) with scrollable bounds (`overflow: visible`) in `.snap-section`, scaled up top paddings to `6.5rem` to prevent header overlaps, and decreased input sizes, margins, and gaps inside the wizard and form components.
- **Header Space Elimination in Results:** Solved the blank space bug in the results screen by dynamically hiding `.wizard-header`, `.wizard-body` (with its 180px min-height constraints), and `.wizard-progress-bar` upon completion, fully reclaiming vertical space in the results panel.
- **Official SVG Logo Vectorization:** Replaced the previous hand-drawn approximations in the navbar, footer, and dynamic favicons (`favicon-brand.svg`, `favicon-dark.svg`, and `favicon.svg`) with the exact mathematical vector paths extracted from the official logo asset provided by the user (`Screenshot 2026-08-03 172512.svg`). Positioned and centered the monogram horizontally and vertically inside a standardized 1:1 round-corner container (`rx="120"`) using CSS variables to dynamically adapt colors per theme.
