# Layout Patterns and Conversion Objectives Guide

This document details different web design layout patterns, their cognitive and brand communication implications, and their recommended conversion objectives or Call-to-Action (CTA) targets.

---

## Viewport Sizing and Responsiveness Constraints

To align with the project's strict core design requirements, all layout patterns implemented on the website must satisfy the following viewport constraints:

1. **Full-Viewport Sizing (`100dvh`):** Every layout section must act as a single visual block filling exactly 100% of the visible viewport height under maximized browser windows. The CSS styling must utilize:
   ```css
   .section-container {
       height: 100vh;      /* Standard fallback */
       height: 100dvh;     /* Dynamic viewport for mobile safe boundaries */
       min-height: 100dvh; /* Enforce full structural enclosure */
   }
   ```
2. **Target Dimensions Adaptation:** Layout designs must adapt fluidly without element collision or content truncation across the following target resolutions specified in the development guidelines:
   * **1920×1080 (Full HD):** Desktop standard for corporate workstations and mid-range laptops.
   * **1536×864:** baselines applying 125% OS scaling.
   * **1366×768:** Legacy and budget laptop resolutions.
   * **1280×1200:** Virtualized Remote Desktop (RDP) environments.
   * **800×600:** Industrial and legacy terminals.
   * **Mobile Viewports (iOS & Android):** Dynamic viewports that must account for expanding/collapsing browser chrome.
3. **Overflow and Content Containment:** If a layout's content density exceeds the vertical limit of `100dvh` on lower resolutions or mobile screens, developers must implement one of these defensive styling strategies:
   * **Internal Vertical Scroll (`overflow-y: auto`):** For text-heavy, sequential reading blocks where vertical continuity is required.
   * **Horizontal Carousel Layout:** For card structures, image galleries, catalogs, or option menus to allow swipe-navigation without breaking the vertical viewport limit.
4. **Alternating Background Colors:** To maintain high visual engagement and establish clear boundaries between snap-sections, consecutive layouts must alternate their background colors. A layout's background color may repeat later in the flow, but it must never be identical to the background color of its immediate predecessor. Furthermore, all background colors must strictly belong to the project's official graphical brand identity (as defined in the global design variables).

---

## 1. Single-Column / Reading Layout
* **What it communicates:** Absolute focus, minimalism, editorial authority, and zero distractions. It is the gold standard for consuming long-form content, emulating the reading experience of a book or printed article.
* **Conversion Objective / CTA:**
  * Newsletter subscription at the end of the article.
  * Download of related resources (eBooks, Whitepapers).
  * **Micro-conversion:** Time spent on page (Scroll depth).

---

## 2. Grid / Card-Based Layout
* **What it communicates:** Variety, equal importance of items, visual exploration, and dynamism. Emulating a catalog or discovery board (like Pinterest or e-commerce), it signals to the user that multiple options are available with the same hierarchical weight.
* **Conversion Objective / CTA:**
  * Clicking on a specific item to start the purchase flow (Add to Cart / View Details).
  * Product filtering and segmentation.
  * **Micro-conversion:** Interaction with multiple cards within a single session.

---

## 3. Split-Screen Layout
* **What it communicates:** Duality, binary choice, and immediate flow personalization. It is ideal when the website serves two clearly differentiated audiences (e.g., B2B vs. B2C) or when contrasting a before-and-after scenario or two equivalent product options.
* **Conversion Objective / CTA:**
  * Sales funnel bifurcation ("I am a Company" vs. "I am a Professional").
  * Direct registration in one of the two options presented competitively.

---

## 4. F-Shape Layout (F-Pattern)
* **What it communicates:** Efficiency, structured data-dense layout, and top-to-bottom prioritization. Based on the natural eye movement of humans scanning text-heavy pages, it places critical information in the top-left corner and along the first horizontal lines.
* **Conversion Objective / CTA:**
  * Clicking the main CTA button in the top-right corner (Header CTA) or immediately after the first horizontal block of text (Hero section).
  * Rapid consumption of key benefits before attention wanes.

---

## 5. Z-Shape Layout (Z-Pattern)
* **What it communicates:** Continuous visual narrative, rhythm, and natural progression. Designed for pages with low text density and high visual impact (standard landing pages), it guides the eye from the logo (top-left corner), across the menu, down diagonally through the visual content, and lands on the opposite bottom corner.
* **Conversion Objective / CTA:**
  * The final CTA is placed at the end of the "Z" (bottom-right corner of the scanning area or centered at the end of the diagonal). Typically: "Sign Up for Free", "Get Started Now", or "Schedule a Demo".

---

## 6. Asymmetrical Layout
* **What it communicates:** Innovation, modernity, disruption, and brand dynamism. By deliberately breaking traditional symmetry rules, it creates points of visual tension that capture the user's attention in a bold, artistic way. Frequently used by creative agencies, high-end portfolios, or premium products.
* **Conversion Objective / CTA:**
  * Qualified leads for custom projects ("Let's work together").
  * Exploration of high-value interactive portfolios.

---

## 7. Single-Page / One-Page Layout
* **What it communicates:** Simplicity, total narrative control, and a linear path with no detours. It prevents the user from getting lost in complex menus; the entire value proposition is packaged into a single vertical flow.
* **Conversion Objective / CTA:**
  * Direct and single conversion target (focused Lead Generation).
  * App download or single-product purchase.

---

## 8. Zig-Zag / Alternating Layout (Horizontal Bands)
* **What it communicates:** Balance, explanatory clarity, and a pedagogical step-by-step approach. Alternating image and text blocks from left to right sequentially prevents visual fatigue and allows detailed breakdown of complex technical features of a product or SaaS.
* **Conversion Objective / CTA:**
  * Keeping the scroll active through intermediate secondary CTAs ("Learn more about this feature").
  * Closing with a primary CTA at the end of the explanatory journey ("Try the tool").

---

Should a specific technical or business objective require defining the structure of a page, we can analyze which of these patterns best aligns with the requirements of your current pipeline.
