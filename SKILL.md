---
name: html-to-elementor
description: "Universal future-proof engine for converting static HTML/CSS/JavaScript websites into native, fully-editable WordPress Elementor pages, theme components, and exportable/importable JSON templates without HTML dumping."
risk: safe
source: user-global
date_added: "2026-10-19"
compatibility:
  models: ["Gemini 3+", "Claude 3.7+", "GPT-4o/o1/o3+", "DeepSeek R1/V3+", "Llama 3.3/4+", "Codex"]
  runtimes: ["Antigravity", "Claude Code", "Cursor", "Windsurf", "Cline/Roo", "Aider", "Copilot"]
  wordpress_versions: ["6.x", "7.x+"]
  elementor_versions: ["3.18+", "3.24+", "4.x+"]
---

# Universal HTML to Elementor Conversion Engine
### Autonomous, Future-Proof Agent Framework for Pixel-Perfect WordPress CMS Synthesis

A universal, model-agnostic, and future-proof skill designed for frontier AI reasoning agents (Google Gemini, Anthropic Claude, OpenAI o1/o3/GPT-4o, DeepSeek, and open models) across modern coding runtimes (Antigravity IDE, Claude Code, Cursor, Windsurf, Cline, Aider).

---

## 1. Core Philosophy & Non-Negotiable Standards

When this skill is activated, the agent operates simultaneously as a **Principal WordPress Architect**, **Senior Elementor Engineer**, and **Forensic Frontend Specialist**.

### A. True Native Editability (Strict Anti-HTML-Dump Mandate)
* **Zero Raw HTML Dumps**: Never dump raw static HTML into an `html` widget or `<iframe>`. A template where content cannot be directly clicked and edited by a client in Elementor is considered a failed conversion.
* **Atomic Widget Mapping**:
  * Headings (`<h1>`-`<h6>`) ➔ Native `heading` widgets with typography, font family, tag hierarchy, and color tokens.
  * Paragraphs and lead copy (`<p>`, `<span>`) ➔ Native `text-editor` widgets.
  * Call-to-actions (`<a>`, `<button>`) ➔ Native `button` widgets with hover states, paddings, and pill radii.
  * Media (`<img>`, `<picture>`, `<svg>`) ➔ Native `image` or `icon` widgets.
  * Bullet items and feature points (`<ul><li>`) ➔ Native `icon-list` widgets.
* **Modern Flexbox & CSS Grid Containers**: Layouts must be built exclusively using Elementor's Container architecture (`elType: "container"`), configuring `flex_direction`, `justify_content`, `align_items`, `gap`, or `container_type: "grid"` inside native controls.
* **Scoped Enhancements Only**: Reserve `settings.custom_css` strictly for glassmorphism (`backdrop-filter`), keyframes, pseudo-elements (`::before`/`::after`), or advanced gradient animations.
* **Zero Entity Sanitization Bugs**: In `custom_css`, never use direct child combinator (`>`) because WordPress database sanitization filters convert it into `&gt;`. Always use descendant whitespace selectors (`selector .child-class`).

### B. Pixel-Perfect Design Fidelity
* **Token Extraction**: Honor exact design tokens (colors, gradients, modular typography, line heights, letter-spacing, radii, box shadows, margins, and paddings).
* **Responsive Breakpoints**: Explicitly define values across all three standard viewports:
  * Desktop (base keys)
  * Tablet (`_tablet` keys: 768px - 1024px)
  * Mobile (`_mobile` keys: <= 767px)
* **Bidirectional Layouts (RTL / LTR)**: Native support for RTL (Arabic, Hebrew, Persian) and LTR (English, Latin), maintaining proper text alignment and flex reversal.

### C. Universal, Stack-Agnostic & Future-Proof
* Works seamlessly across vanilla HTML/CSS, Tailwind CSS, Bootstrap, modern CSS Grid/Subgrid, single-page portfolios, and multi-page corporate web architectures.
* Fully compatible with modern WordPress 6.x/7.x and Elementor 3.x/4.x+.

### D. Zero-Bandwidth & Privacy Protocol
* Execute all parsing, AST analysis, template generation, schema validation, and reporting **100% locally on the host machine**.
* No external web scraping or dependency downloads required.

---

## 2. Five-Phase Autonomous Workflow

```
┌──────────────────────────────────────────────┐
│ Phase 1: Forensic Discovery & Token Parsing   │
└──────────────────────┬───────────────────────┘
                       │
┌──────────────────────▼───────────────────────┐
│ Phase 2: Strategy Definition (JSON vs API)   │
└──────────────────────┬───────────────────────┘
                       │
┌──────────────────────▼───────────────────────┐
│ Phase 3: Atomic Elementor Synthesis Engine   │
└──────────────────────┬───────────────────────┘
                       │
┌──────────────────────▼───────────────────────┐
│ Phase 4: Automated Verification & Correction │
└──────────────────────┬───────────────────────┘
                       │
┌──────────────────────▼───────────────────────┐
│ Phase 5: Client-Ready Packaging & Reporting  │
└──────────────────────────────────────────────┘
```

---

### Phase 1: Forensic Discovery & Token Parsing
1. **Asset & Structure Inventory**:
   * Scan local repository to identify all HTML pages, CSS files, JavaScript scripts, images, SVG icons, and web fonts.
   * Document page hierarchy, reusable partials (Header, Footer, Navigation, Modals, Call-to-Actions), and dynamic widgets.
2. **Design System Forensic Extraction**:
   * Inspect stylesheet roots (`:root`, `tokens.css`, Tailwind config, or inline styles).
   * Construct an internal palette and typography map:
     * Primary, secondary, surface, and accent colors.
     * Font families, weights, and modular type scales.
     * Container max-widths, section vertical padding, and grid gutters.
3. **Interactive & JS Behavior Audit**:
   * Catalogue interactive elements: dropdowns, mobile navigation drawers, sliders (e.g. Swiper), tabs, filterable grids, modals, accordions, and contact forms.
   * Classify each interaction:
     * *Native Elementor*: Standard widgets, nested tabs, or Menu widgets.
     * *CSS-Driven*: Transitions, keyframes, or `:hover` states.
     * *Custom Script*: Lightweight, scoped vanilla JavaScript.

---

### Phase 2: Strategy Definition

#### Mode A: Standalone Elementor JSON Templates (Primary)
* Generate importable templates (`*-importable.json`) conforming to Elementor's export schema:
  `{ "version": "0.4", "title": "...", "type": "page|section", "content": [...] }`
* Also generate raw `_elementor_data` JSON arrays for direct database/API ingestion.

#### Mode B: Full WordPress Deployment (When WP Environment is Available)
* Verify WordPress & Elementor version and active features (Flexbox Containers experiment status).
* Create/update pages via REST API (`/wp-json/wp/v2/pages` and `_elementor_data` postmeta).
* Configure Global Header/Footer templates.

---

### Phase 3: Atomic Elementor Synthesis Engine

1. **Outer Containers**:
   Map each HTML `<section>` to an outer Elementor container:
   ```json
   {
     "id": "sec_hero",
     "elType": "container",
     "isInner": false,
     "settings": {
       "content_width": "boxed",
       "boxed_width": { "unit": "px", "size": 1200 },
       "flex_direction": "column",
       "padding": { "unit": "px", "top": "100", "right": "24", "bottom": "100", "left": "24", "isLinked": false }
     },
     "elements": [ ... ]
   }
   ```
2. **Inner Flex / Grid Wrappers**:
   Transform nested grid/flex wrappers (`.row`, `.grid`) into child containers (`"isInner": true`).
3. **Atomic Widget Transformation**:
   * Replace every text tag with native `heading` or `text-editor`.
   * Replace buttons with `button` widgets.
   * Replace images with `image` widgets.
   * Replace icon lists with `icon-list` widgets.
4. **Micro-CSS Scoping**:
   Apply `settings.custom_css` strictly using the `selector` keyword and descendant whitespace selectors.

---

### Phase 4: Automated Verification & Correction

Never deliver a template without local automated verification:

```bash
python "<SKILL_DIR>/scripts/validate_elementor_template.py" "<PATH_TO_GENERATED_TEMPLATE.json>"
```

**Verification Gate Checklist:**
* [x] **Schema Compliance**: Valid `version: 0.4`, `title`, `type`, and `content` array.
* [x] **Structural Integrity**: Valid `id`, `elType`, `settings`, `elements` on every node.
* [x] **100% ID Uniqueness**: No duplicate element IDs anywhere in the document.
* [x] **Editability Score**: Native widget ratio must exceed 85-90%.
* [x] **Sanitization Security**: Zero `&gt;` entities inside custom CSS blocks.

**Self-Correction Protocol**: If validation flags any warnings or errors, the agent must parse the diagnostic output, locate the faulty container/widget, patch it, and re-run validation until it passes cleanly.

---

### Phase 5: Client-Ready Packaging & Reporting

Deliver the output in a clean, organized structure:

```text
elementor-output/
├── templates/
│   ├── page-home-importable.json          # Ready for Elementor Import Template UI
│   ├── page-about-importable.json
│   ├── section-header-importable.json
│   └── section-footer-importable.json
├── raw-data/
│   ├── page-home.json                     # Raw _elementor_data postmeta
│   └── page-about.json
├── assets-manifest.json                   # List of images/fonts used and WP target paths
├── README-IMPORT-GUIDE.md                 # Clear, concise import instructions
└── VERIFICATION-REPORT.md                 # Forensic audit results & editability scores
```

---

## 3. Reference Documentation & Tooling

* **Schema Specification**: Refer to [`references/elementor-template-schema.md`](references/elementor-template-schema.md) for full Container JSON schemas, widget models, responsive suffix conventions, and property tables.
* **Validation Script**: Use [`scripts/validate_elementor_template.py`](scripts/validate_elementor_template.py) to validate any JSON template instantly with zero external dependencies.
