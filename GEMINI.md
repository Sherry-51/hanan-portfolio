# TikTok Shop Growth Specialist Portfolio - GEMINI.md

This document serves as the primary instructional context for Gemini when interacting with this codebase.

## Project Overview

**Purpose:** A high-performance, premium portfolio website for a TikTok Shop Growth Specialist. The site showcases expertise in viral marketing, shoppable content, and influencer partnerships.

**Core Value Proposition:** Scaling brands on TikTok Shop to 7-figures through data-driven strategies and direct expertise (no junior account managers).

**Target Audience:** TikTok Shop brand owners, e-commerce founders, and digital marketing directors.

### Tech Stack

- **Frontend:** Vanilla HTML5, CSS3, and JavaScript (ES6+).
- **Design System:** Custom CSS design system using CSS Variables for consistent branding (TikTok Black, Razzmatazz, Splash).
- **Typography:** Google Fonts (Playfair Display for headings, DM Sans for body).
- **Icons:** Inline SVGs and simple character-based social icons.
- **Interactions:** Custom JavaScript-driven animations (Intersection Observer, Parallax, Number Counters, Carousel).

### Architecture & File Structure

The project follows a flat structure for simplicity and fast loading:

- `index.html`: The main landing page featuring the hero section, expertise overview, featured case studies, and testimonials.
- `about.html`: Detailed professional background and philosophy.
- `case-studies.html`: A filterable grid of real-world client transformations.
- `contact.html`: Consultation booking and free audit request form.
- `privacy.html` & `terms.html`: Standard legal documentation.
- `styles.css`: Central stylesheet containing the design system, layout, and component styles. **Note:** Currently contains some redundancy in mobile media queries.
- `app.js`: Central logic for interactions, animations, and UI state management.

## Building and Running

**Running Locally:**
As this is a static project, it can be run by opening any `.html` file in a browser. For development, a simple local server like `live-server` or `npx serve .` is recommended to handle asset paths and live reloading.

**Commands:**
- TODO: Add build script if a bundler (like Vite or Parcel) is introduced.
- TODO: Add linting commands for HTML/CSS/JS.

## Development Conventions

### 1. CSS Design System
Always use the defined CSS variables in `styles.css` for consistency:
- Backgrounds: `--bg-primary`, `--bg-secondary`
- Text: `--text-primary`, `--text-secondary`
- Accents: `--accent-action`, `--accent-secondary`

### 2. Component Class Naming (BEM-lite)
The project uses a naming convention similar to BEM (Block Element Modifier):
- Blocks: `.nav`, `.hero`, `.case-study`, `.footer`
- Elements: `.nav__links`, `.hero__title`, `.footer__column`
- Modifiers: `.btn--primary`, `.hidden-element--fade`

### 3. Responsive Design
- The site follows a "Mobile-First" approach for many components, with significant overrides in media queries for larger screens.
- **Breakpoints:**
  - Mobile: `< 768px` (Primary mobile breakpoint)
  - Desktop: `> 768px`
  - Small Mobile: `< 480px`

### 4. Interactive Elements
Animations are triggered using the `.hidden-element` class and the `IntersectionObserver` in `app.js`. When adding new sections:
1. Wrap elements in `hidden-element` or its variants (`hidden-element--fade`, `--left`, etc.).
2. The `IntersectionObserver` will automatically add the `in-view` class when the element enters the viewport.

### 5. Navigation & UI Patterns
- **Mobile Menu:** Controlled by `.nav__mobile-toggle` and `.nav__links.open`.
- **Footer Accordion:** Footer columns should have the `.collapsed` class by default in HTML; `app.js` handles toggling on click.
- **Testimonial Carousel:** Auto-scrolls every 2 seconds when in view.

## Maintenance Notes
- **Redundancy:** There are multiple blocks of `@media (max-width: 767px)` in `styles.css`. When making mobile changes, ensure all blocks are kept in sync or consider a refactor to consolidate them.
- **Counters:** Use `data-counter` on elements where numeric growth animations are desired. The script handles decimals if the `data-counter` value contains a period.
