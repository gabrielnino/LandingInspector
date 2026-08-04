# Methodological Bunker: Development Guidelines and Project Innegotiables

**Project:** Corporate Institutional Website  
**Human Strategist / Founder:** Luis Gabriel Niño[cite: 2]  
**Executor / AI Assistant:** AI Swarm / Antigravity Orchestrator[cite: 2]  

---

## Table of Contents
1. [Statement of Principles and Governance](#1-statement-of-principles-and-governance)
2. [Project Innegotiables (Golden Rules)](#2-project-innegotiables-golden-rules)
3. [Technology Stack and Infrastructure](#3-technology-stack-and-infrastructure)
4. [Information Architecture and Code Structure](#4-information-architecture-and-code-structure)
5. [Quality Contract: Antigravity Pipeline](#5-quality-contract-antigravity-pipeline)
6. [Naming Standards and Directory Structure](#6-naming-standards-and-directory-structure)

---

## 1. Statement of Principles and Governance

This document establishes the strict and non-negotiable methodological framework under which **Antigravity** and any AI agent will operate for the construction, evolution, and maintenance of the institutional website[cite: 2].

Development is governed under a philosophy of **clean architecture, radical time optimization, and absolute elimination of cognitive dispersion**[cite: 2]. The AI acts as the executing arm and tool user; strategic control and decision-making remain with the Human Founder[cite: 2].

---

## 2. Project Innegotiables (Golden Rules)

Any increment of code, component, or configuration that violates the following points will be **automatically rejected** by the pipeline before its deployment[cite: 2]:

* **SEO Hyper-Optimization, Clean Semantics, and Speed:** The site must maintain a minimum score of **95/100** in *Performance* and *SEO* on Google PageSpeed Insights / Lighthouse[cite: 2]. To enforce this, the following practices are mandatory[cite: 2]:
    1.  **Semantic HTML Structure:** Use correct HTML5 structural tags (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)[cite: 2].
    2.  **Strict Headings Hierarchy:** Maintain exactly **one `<h1>` tag per page** representing the primary title, with subordinate subtitles sequentially organized under `<h2>`, `<h3>`, etc[cite: 2].
    3.  **Unique Titles & Descriptions:** Ensure unique `<title>` (under 60 characters) and `<meta description>` (under 160 characters) elements are configured per page[cite: 2].
    4.  **Accessible Asset Descriptors:** Obligatorily declare meaningful and descriptive `alt` attributes on all images[cite: 2].
    5.  **Descriptive Anchor Links:** Do not use vague link text (such as "click here" or "read more"); always use descriptive anchor text[cite: 2].
    6.  **Structured Schema Markup:** Where appropriate, implement structured data using JSON-LD (Schema.org) to facilitate search engines understanding site context[cite: 2].
    7.  **Canonical URLs:** Ensure that every page/section of the site dynamically constructs and declares its canonical URL to point to the production domain (`https://your-domain.com`), preventing search engine indexing of staging or preview URLs[cite: 2].
    8.  **Minimal Client-Side JS:** Client-side JavaScript usage must tend to zero[cite: 2].

* **Viewport-Proportional Layout Strategy:** To ensure a web page that layout-adapts across multiple resolutions where each section or segment occupies exactly the vertical screen size, the technical layout approach must combine Responsive Web Design with CSS Viewport units[cite: 2].
    1. **Strict Core Sizing (Mobile & Dynamic Safeties):** To prevent navigation bar clipping, content overflowing, or artificial scrolling on Android and iOS devices caused by dynamic browser chrome, developers must utilize dynamic viewport units with fallback values[cite: 2]. Every main segment container must implement[cite: 2]:
        ```css
        .section-container {
            height: 100vh;      /* Standard fallback for legacy browsers */
            height: 100dvh;     /* Dynamic viewport sizing for modern mobile environments */
            min-height: 100dvh; /* Guarantees complete vertical structural enclosure */
        }
        ```
       Utilizing the dynamic viewport (`dvh`) guarantees that each individual section acts as a "single block" filling exactly 100% of the browser's visible height, dynamically adapting when mobile address bars expand or collapse[cite: 2].
    2. **Internal Distribution and Strict Overflow Containment:** To handle design flexibility and internal element positioning inside each vertical section, CSS Flexbox or CSS Grid must be implemented[cite: 2]. These layout tools allow automatic vertical and horizontal content centering[cite: 2]. If content density within a container threatens to break the `100dvh` boundary on smaller devices, developers must apply one of the following two defensive techniques depending explicitly on the nature of the data:
        * **Internal Vertical Scroll (`overflow-y: auto`):** To be implemented strictly when the target content is heavily textual, designed for sequential reading, or possesses an absolute narrative density that demands complete vertical continuity within the isolated block[cite: 2].
        * **Horizontal Carousel Layout:** To be implemented as the mandatory architectural alternative when the overflowing elements constitute an options menu, item/product catalogs, image galleries, or structural card layouts that natively permit horizontal swipe navigation, thus completely safeguarding the section's vertical viewport restrictions.
    3. **Orientation Responsiveness:** Strategic Media Queries must complement this structure to readjust font sizes, padding, margins, and content flow when the viewport transitions between landscape and portrait orientations, ensuring a seamless user experience and strict space containment across all screen targets[cite: 2].
    4. **Top Return Navigation:** Each viewport-proportional section (excluding the primary Hero Section) must include a clean, recognizable icon link (e.g., a home or arrow-up icon) positioned consistently in a corner to allow users to return instantly to the top/main page (Hero section), ensuring frictionless vertical navigation[cite: 2].

* **Complete Code Delivery:** The AI is strictly forbidden from generating code blocks with *placeholders*, elision comments (`// TODO: implement here`), or incomplete structures[cite: 2]. Each delivery must be a functional, clean, and self-contained block[cite: 2].
* **Real Multi-Device Testing Focus:** Generic mock validations are not accepted[cite: 2]. E2E and UI validation suites must emulate real rendering engines, incorporating target mobile devices alongside the most representative desktop screen resolutions based on global web traffic analytics[cite: 2]:

| Resolution | Aspect Ratio | Desktop Traffic Share | Context / Use Case |
| :--- | :--- | :--- | :--- |
| **1920×1080 (Full HD)** | 16:9 | **17.57%** | Absolute market standard for corporate workstations and mid-range laptops.[cite: 2] |
| **1280×1200** | 16:15 | **9.58%** | Highly prevalent in virtualized environments and Remote Desktop (RDP) sessions.[cite: 2] |
| **1366×768** | 16:9 | **5.85%** | Legacy budget laptops and older enterprise hardware fleets.[cite: 2] |
| **1536×864** | 16:9 | **7.15%** | Common native baseline for modern laptops applying 125% OS-level scaling.[cite: 2] |
| **800×600** | 4:3 | **7.26%** | Legacy infrastructure, industrial terminals, and embedded systems.[cite: 2] |

    *Target Engines:*
    1.  **Desktop:** Google Chrome (Blink) validating the core matrix layouts above[cite: 2].
    2.  **iOS (iPhone):** Safari (WebKit)[cite: 2].
    3.  **Android:** Google Chrome (Blink)[cite: 2].

    *Mandatory Automated Visual and Resolution Testing:*
    1.  **Resolution-Based Assertions:** Automated tests (E2E/Component tests using Playwright, Cypress, or Vitest/Puppeteer) must be explicitly written to execute and render the page under each of the defined target resolutions (from 1920x1080 down to mobile viewports)[cite: 2].
    2.  **Rendering Engine Emulation:** Test suites must run across all three target rendering engines (Chromium/Blink, WebKit, and Firefox/Gecko) to ensure consistent layout behavior[cite: 2].
    3.  **Visual Overlap and Collision Audits:** The automated test suite must programmatically verify that all interactive components (buttons, links, inputs) and copy elements remain visible, legible, and do not collide, overlap, or hide behind one another (z-index overlaps, absolute positioning text clipping, or overflow clipping)[cite: 2].
    4.  **No Hidden Elements:** Visual regression or DOM element position boundary tests must assert that no essential B2B copy or call-to-action buttons are pushed out of the viewport bounds or obscured by overlay elements (such as headers, floating elements, or dev tools)[cite: 2].

* **Dynamic SEO Loop:** Every technical iteration or content alteration requires an automatic recalculation of the keyword map and metadata audit[cite: 2].
* **Real-World Metrics Without Penalty:** The presence of **Google Analytics 4 (GA4)** and **Vercel Analytics** is mandatory[cite: 2]. However, their loading must be optimized (e.g., via deferred script loading) so that under no circumstances do they penalize the Time to Interactive (TTI) or degrade performance[cite: 2].
* **Language Standard (English Core):** English is and will always remain the sole language for all internal and external project development resources[cite: 2]. This includes source code, components, CSS variables, unit and E2E tests, configuration files, git commit messages, pull requests, folders, file names, and documentation[cite: 2]. This standard applies universally even if the public-facing user interface supports multiple languages (multilingual localization)[cite: 2].
* **Test Coverage & Technical Debt Control:** The codebase must maintain a minimum of **80% code coverage**[cite: 2]. We cannot allow technical debt to rise above 20% (preventing untested logic from exceeding 20% of the codebase)[cite: 2]. Any code submission that drops coverage below this 80% threshold will be automatically rejected[cite: 2].
* **Mandatory Changelog Logging:** Every change committed to the repository must be documented in `doc-changelog.md` under the appropriate release header, using Keep a Changelog formatting rules (Added, Changed, Deprecated, Removed, Fixed, Security)[cite: 2].
* **Cohesive Artifact Naming and Mnemonic Standard:** All project files, documentation, designs, plans, and technical assets (herein referred to as artifacts) must adhere to a strict, cohesive naming convention incorporating clear mnemonics to indicate their domain and content[cite: 2]:
    1.  **Format Constraints:** All filenames must be lowercase, using alphanumeric characters, and using hyphens (`-`) as separators (kebab-case)[cite: 2]. Special characters, spaces, and capital letters are strictly forbidden[cite: 2].
    2.  **Mnemonic Prefixes:** Filenames must be prefixed with a descriptive mnemonic category tag[cite: 2]:
        * `doc-`: For permanent project documentation, guidelines, and manuals (e.g., `doc-development-guidelines.md`, `doc-brand-book.md`)[cite: 2].
        * `plan-`: For implementation, testing, or architectural plans (e.g., `plan-implementation.md`)[cite: 2].
        * `test-`: For automated test scripts, visual regression assertions, and test suites[cite: 2].
        * `asset-`: For static images, logos, graphics, and vector SVG files[cite: 2].
        * `scratch-`: For temporary helper scripts, playground files, and debugging data[cite: 2].
    3.  **Content Description:** Following the prefix, the filename must contain a brief, self-describing kebab-case descriptor (e.g., `doc-development-guidelines.md`, `asset-logo-transparent.svg`)[cite: 2].
    4.  **Enforced Cohesion:** No ad-hoc, camelCase, or loosely named files may be introduced into the repository structure[cite: 2].

---

## 3. Technology Stack and Infrastructure

The technology selection is designed to minimize operational costs, eliminate server maintenance needs, and maximize speed at the *Edge*[cite: 2]:

* **Core Framework:** Astro (Static Site Generation - SSG)[cite: 2]. Pure compile-time rendering[cite: 2].
* **Styling:** Tailwind CSS (Mobile-First approach, utility classes optimized via production purging)[cite: 2]. *Note: The current workspace uses Vanilla CSS for performance and speed reasons, but the framework choice remains standard.*[cite: 2]
* **Version Control:** GitHub (Private repository, integration base of operations)[cite: 2].
* **Deployment and Hosting:** Vercel (Freemium / Hobby tier)[cite: 2]. Leveraging Edge Network CDN, automatic SSL, and preview URLs per Pull Request[cite: 2].

---

## 4. Information Architecture and Code Structure

### Phase 1 Scope
The scope is strictly limited to a **Positioning Website**[cite: 2]. Interactive software components, complex databases, or SaaS-like dashboards are entirely excluded to reduce initial cognitive load[cite: 2].

The site consists of exactly 5 sections (each requiring its own canonical URL pointing to the production domain)[cite: 2]:
1.  Home: High-conversion business-oriented landing page[cite: 2].
2.  Services: Catalog and description of the core offering[cite: 2].
3.  AI Systems: Strategic space to position automation and swarm capabilities[cite: 2].
4.  Cases: Case studies and technical success validations[cite: 2].
5.  About Us: Brand identity, vision, and corporate backing[cite: 2].

### Code Organization: Feature-Driven
The project will not use a purely global atomic structure[cite: 2]. It will be organized **by feature (Feature-Driven)**[cite: 2]. Each of the 5 sections will have its own isolated module with its specific components and layouts[cite: 2]. Only cross-cutting elements (Header, Footer, Base Buttons) will reside in a shared folder (`shared`)[cite: 2].

---

## 5. Quality Contract: Antigravity Pipeline

**Antigravity** will execute tasks strictly based on the following two control contracts[cite: 2]:

### Definition of Ready (DoR) - When can we start?
A requirement or task is ready for the AI to write code only if it has[cite: 2]:
1.  The required Astro component map perfectly defined[cite: 2].
2.  The structured data schema (if consuming local Markdown or JSON)[cite: 2].
3.  The final copies approved by the strategist[cite: 2].

### Definition of Done (DoD) - When is it finished?
A code increment is considered "Done" and ready for production if and only if it automatically complies with[cite: 2]:
* **Unit Tests:** Executed in **Vitest** with **Testing Library**, validating properties injection and correct rendering of the Astro structure[cite: 2].
* **Integration and UI Tests (E2E):** Executed in **Playwright** obligatorily simulating the target mobile devices (iOS/Android) and desktop profiles[cite: 2].
* **Code Coverage Verification:** Enforce that test coverage meets or exceeds the **80% minimum threshold** (technical debt ratio below 20%) before any deployment[cite: 2].
* **Deployment Filter (Lighthouse CI):** Automatic block of Vercel deployment if the audit yields a score below 95 in performance or SEO[cite: 2].
* **Strict Tag and Analytics Validation:** Mandatory presence of `<title>`, `meta description`, canonical links (`<link rel="canonical">`), Open Graph tags (`og:*`), image `alt` attributes, and validation of correct initialization and zero performance impact of GA4 and Vercel Analytics scripts[cite: 2].
* **Changelog Sync:** Verify that `doc-changelog.md` has been updated with standard entries documenting the changes before finalizing a task[cite: 2].

---

## 6. Naming Standards and Directory Structure

### Mnemonic Prefix Taxonomy (Strictly enforced without exception)
All files and directory resources in the repository must be named in lowercase, using alphanumeric characters, with hyphens (`-`) as separators, and must carry one of the following mnemonic prefixes[cite: 2]:

* **Pages (Astro Routes):** Must be prefixed with `page-` (e.g., `page-index.astro`, `page-services.astro`)[cite: 2].
    *Technical Routing Integration:* To align with Astro's file-based routing while maintaining the mnemonic prefix on the filesystem, the home page is named `page-index.astro` and the root path `/` is mapped via redirects in `astro.config.mjs` or by importing the component[cite: 2].
* **Astro Components:** Must be prefixed with `comp-` (e.g., `comp-navbar.astro`, `comp-footer.astro`)[cite: 2].
* **Stylesheets:** Must be prefixed with `style-` (e.g., `style-global.css`, `style-variables.css`)[cite: 2].
* **Unit & E2E Tests:** Must be prefixed with `test-` (e.g., `test-comp-navbar.ts`, `test-page-index.ts`)[cite: 2].
* **Design & Business Documentation:** Must be prefixed with `doc-` (e.g., `doc-development-guidelines.md`, `doc-brand-book.md`, `doc-[project-name]-icp.md`, `doc-[project-name]-story-telling.md`)[cite: 2].
* **Images & Graphical Assets:** Must be prefixed with `asset-` (e.g., `asset-logo-final.svg`, `asset-logo-final.jpg`, `asset-favicon.svg`)[cite: 2].

### Folder Structure
```text
# El árbol de directorios permanece intacto según las especificaciones de arquitectura limpia establecidas.