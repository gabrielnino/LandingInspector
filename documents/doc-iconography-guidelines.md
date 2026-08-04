# Iconography System Guidelines

**Brand Document Identifier:** `doc-iconography-guidelines`  
**Classification:** Design & Business Documentation  
**Version:** 1.0.0  
**Date:** July 17, 2026  

---

## 1. Introduction & Objectives

This document establishes the unified technical and aesthetic standards for the iconography system. The objective is to ensure visual harmony, scalability, and code performance across all digital touchpoints and user interfaces. 

Icons serve as critical visual anchors that guide navigation, highlight primary calls to action (CTAs), and reinforce brand communication consistently.

---

## 2. Icon Style & Aesthetic DNA

To ensure consistency with modern, geometric typefaces and clean UI layouts, all icons must adhere to the following design constraints:

```
          ┌────────────────────────────────────────┐
          │               ICON STYLE               │
          ├─────────────────┬──────────────────────┤
          │ Type            │ Outline (Stroke-based│
          ├─────────────────┼──────────────────────┤
          │ Stroke Weight   │ 1.5px (Default/MD)   │
          ├─────────────────┼──────────────────────┤
          │ Corner Radius   │ 2px to 4px (Rounded) │
          ├─────────────────┼──────────────────────┤
          │ Cap & Join      │ Round (stroke-linecap│
          └─────────────────┴──────────────────────┘
```

* **Outline Style:** Icons for standard UI controls must be built using vector paths rather than solid fills. This ensures high rendering clarity at low resolutions.
* **High-Fidelity Branded Badges:** For core section highlights and content pages, icons are styled as high-fidelity illustration badges inspired by the brand logo (incorporating the Chiva roof luggage rack, tricolor curved brushstrokes, and red Canadian maple leaf details on a cream background).
* **Unified Stroke Weight:** Standard outline icons use a consistent stroke weight of `1.5px` (on 24px canvases). Branded badges utilize layered outlines of `1.5px` to `2.5px` to maintain depth and visual richness.
* **Softened Geometry (Rounded Corners):** Sharp corners are strictly prohibited. Corners must carry a `2px` to `4px` radius (for standard icons) or `6px` to `8px` (for outer badge boundaries) to match the curved cursive script elements of the logo.
* **Open Paths and Terminals:** Stroke ends (`stroke-linecap`) and corners (`stroke-linejoin`) must be set to `round` to convey warmth and organic fluidity.
* **Brand Color Palette Fills:** Branded illustration badges incorporate solid vector fills in Colombian Yellow (`#FCD116`), Deep Navy Blue (`#122C54`), Canadian Red (`#CE1126`), and Heritage Cream (`#F4F1E6`) to reflect the exact colors of the official logo.

---

## 3. Retícula & Canvas Boundaries (24x24 px Grid)

Icons must be designed within a standardized vector bounding box to ensure proper optical centering and alignment.

```
       ┌─────────────────────────────────────────────────┐
       │   2px Outer Safe Zone Padding (No vectors)      │
       │  ┌───────────────────────────────────────────┐  │
       │  │                                           │  │
       │  │       20px Vector Drawing Area            │  │
       │  │                                           │  │
       │  │                                           │  │
       │  │                                           │  │
       │  │                                           │  │
       │  │                                           │  │
       │  └───────────────────────────────────────────┘  │
       └─────────────────────────────────────────────────┘
       ◄──────────────────── 24px ──────────────────────►
```

* **Target Box size:** `24px` x `24px` standard canvas for UI controls; `48px` x `48px` expanded canvas for high-fidelity branded illustration badges.
* **Safe Zone Padding:**
  * For `24px` standard icons: A mandatory `2px` outer padding boundary is kept clear. Active vectors sit within the inner `20px` x `20px` zone.
  * For `48px` branded badges: A `4px` safe margin is applied to inner symbols. The outer badge boundaries sit within `2px` of the edge. The top `4px` are dedicated to the Chiva roof luggage rack accent, and the bottom `8px` house the curved tricolor paint stroke.
* **Optical Alignment:** Center the weight of the icon mathematically and visually. Elements with heavy asymmetric features must be manually shifted to guarantee correct optical balance relative to adjacent text.

---

## 4. Categorized Semantic Sets

The iconography system is organized into five functional categories matching common website and NPO architectures:

### A. Navigation & Viewport Set
Icons managing user movement and window control:
* **Arrow Up (`arrow-up`):** Floating viewport return navigation (back-to-top snapping).
* **Arrow Down (`arrow-down`):** Section progression indicators.
* **Menu (`menu`):** Mobile hamburger menu triggers.
* **Close (`close`):** Dismissing dialogs and closing menus.
* **External Link (`external-link`):** Indicating redirect paths out of the portal.

### B. Contact & Communication Set
Icons mapping direct user-business interactions:
* **Phone (`phone`):** Direct clickable telephone links.
* **Mail (`mail`):** Official email channels.
* **Map Pin (`map-pin`):** Event physical addresses and headquarters.
* **Chat (`message-square`):** Direct links to social chats or communities.

### C. Community & Action Set
Icons signifying civic, social, or community initiatives:
* **Users (`users`):** Volunteering, membership directories, and fanbase statistics.
* **Calendar (`calendar`):** Scheduled events, matches, and meetings.
* **Recycle/Civic Duty (`recycle`):** Neighborhood cleaning campaigns and environmental care.
* **Megaphone (`megaphone`):** Public announcements and news updates.

### D. Business & Trust Set
Icons driving conversion in B2B blocks:
* **Handshake (`handshake`):** Commercial alliances and sponsorships.
* **Shield (`shield`):** Data safety, secure processing, and NDA guarantees.
* **Trending Up (`trending-up`):** Metric traction and audience reach data.
* **File Text (`file-text`):** Document sitemaps and bylaws.

### E. Feedback & Status Set
Icons rendering system response:
* **Check Circle (`check-circle`):** Successful form submission.
* **Alert Circle (`alert-circle`):** Warning or informational highlights.
* **X Circle (`x-circle`):** Error reports.

---

## 5. Technical Implementation Guidelines

To maximize accessibility, code efficiency, and design flexibility, all digital implementations must follow these rules:

### A. Inline SVG Over Sprites
To enable dynamic color changes, icons must be rendered as inline SVGs rather than background images or rasterized icons. This allows the icon color to be inherited directly from CSS text color:

```html
<svg 
  xmlns="http://www.w3.org/2000/svg" 
  viewBox="0 0 24 24" 
  width="24" 
  height="24" 
  fill="none" 
  stroke="currentColor" 
  stroke-width="1.5" 
  stroke-linecap="round" 
  stroke-linejoin="round"
  class="icon-class"
  aria-hidden="true"
>
  <!-- Vector paths here -->
</svg>
```

### B. Color Inheritance
By setting `stroke="currentColor"`, the SVG will automatically adapt its color to match the text color of the parent container, ensuring seamless integration during light/dark theme shifts:

```css
.icon-class {
    color: var(--navy-blue); /* Default brand color */
    transition: color 0.2s ease-in-out;
}

.parent-element:hover .icon-class {
    color: var(--accent-red); /* Hover color feedback */
}
```

### C. Standardized Sizing Scale
Use consistent CSS classes to manage sizes across layouts:

| Size Class | Dimensions | Use Case |
| :--- | :--- | :--- |
| `icon-sm` | `16px` x `16px` | Compact buttons, inline links, metadata tags. |
| `icon-md` | `24px` x `24px` | Standard buttons, navigational headers, forms. |
| `icon-lg` | `32px` x `32px` | Feature grid highlights, card-based icons. |
| `icon-xl` | `48px` x `48px` | Major section headers, hero value statements. |

### D. Accessibility Standards (a11y)
1. **Decorative Icons:** If an icon is accompanied by descriptive text, add `aria-hidden="true"` to prevent screen readers from announcing redundant graphical elements.
2. **Interactive Icons:** If the icon acts as a standalone button (e.g. close modal, menu toggle), wrap it in an interactive element with a descriptive text label:
   ```html
   <button aria-label="Close Main Menu">
     <svg aria-hidden="true">...</svg>
   </button>
   ```

---
*End of doc-iconography-guidelines.*
