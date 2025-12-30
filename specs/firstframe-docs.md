# FirstFrame Documentation Wireframes

**STATUS**: Ready for `/wireframe`

## Overview

Wireframes that document FirstFrame itself - showing the wireframe viewer, the workflow, and how to use the product. These wireframes serve as both documentation AND demonstration of the tool's capabilities.

---

## What to Show

### 1. The Wireframe Viewer (the product itself)
The wireframe viewer (`index.html`) is what users see when they visit the demo. Show:
- Sidebar navigation with collapsible sections
- Main SVG viewer area with pan/zoom
- Footer with prev/next buttons, zoom controls
- Focus mode (F key)
- Keyboard shortcuts

### 2. The Workflow
How you use FirstFrame with Claude Code:
- Running `/specify` to create specs
- Running `/wireframe` to generate SVGs
- The two-phase workflow with HARD STOP review checkpoint

### 3. The Story
The storyboard metaphor and value proposition:
- "Every great film starts with a single frame"
- "Specs + Frames = clear vision, properly supported"
- Plan before you code

---

## Wireframes to Generate

### 01 - Viewer Interface
**Canvas**: 1400x800 (standard)
**Theme**: Dark
**Purpose**: Show the FirstFrame wireframe viewer UI

#### viewer.svg
**Layout:**
- Desktop: The full viewer interface
  - Sidebar (220px): "FirstFrame" logo/link, collapsible section "01 - Example" with 3 links showing titles + paths
  - Main viewer area: Display an SVG wireframe showing Desktop|Mobile side-by-side
  - Footer: Prev/Next buttons, zoom controls (-/85%/+), "F(key) to toggle focus mode" hint, counter "1 / 3", GitHub link
- Mobile: Simplified vertical layout
  - Hamburger menu
  - SVG viewer (swipe to navigate)
  - Bottom navigation bar

**Key callouts:**
- Pan & zoom (mouse drag, scroll wheel)
- Keyboard navigation (arrow keys)
- Focus mode (hides chrome)

---

### 02 - Workflow
**Canvas**: 1400x800 (standard)
**Theme**: Dark
**Purpose**: Show how FirstFrame integrates with Claude Code

#### workflow.svg
**Layout:**
- Desktop: Split view showing
  - Left side: Claude Code terminal with command sequence
    ```
    $ claude
    > /specify
    Creating spec from feature description...
    > /wireframe
    Generating SVG wireframes...
    ```
  - Right side: Arrow flow diagram
    - Phase 1: Feature → /specify → /clarify → /wireframe
    - HARD STOP: Review with stakeholders
    - Phase 2: /plan → /tasks → /implement
- Mobile: Vertical timeline of the same workflow

**Key messaging:**
- "Stop coding before you know what you're building"
- "Review wireframes before proceeding"

---

### 03 - Hero/Landing
**Canvas**: 1400x800 (standard)
**Theme**: Dark
**Purpose**: Marketing hero showing the value proposition

#### hero.svg
**Layout:**
- Desktop: Centered hero
  - Film strip icon (FirstFrame logo concept)
  - Headline: "Every great film starts with a single frame"
  - Subheadline: "Plan your project with specs and wireframes before writing code"
  - Two cards:
    - "Specs" - Glasses icon - "Requirements with clarity"
    - "Frames" - Frame icon - "Structure to hold your vision"
  - Tagline: "Specs + Frames = clear vision, properly supported"
  - CTA: "Fork on GitHub" button
- Mobile: Stacked vertical layout

---

### 04 - Component Library
**Canvas**: 1400x800 (standard)
**Theme**: Dark
**Purpose**: Reference for wireframe components

#### components.svg
Show standard wireframe components used in FirstFrame:
- Sidebar navigation patterns
- Card layouts (with shadow, borders)
- Button styles (primary, secondary, icon)
- Form elements (inputs, dropdowns, checkboxes)
- Code blocks / terminal styling
- Status indicators (badges, dots)
- Desktop | Mobile size comparisons

---

## Folder Structure

```
docs/design/wireframes/
├── 01-viewer/
│   └── viewer.svg           (The viewer interface itself)
├── 02-workflow/
│   └── workflow.svg         (Claude Code + workflow diagram)
├── 03-hero/
│   └── hero.svg            (Marketing hero/landing)
└── 04-components/
    └── components.svg      (Component reference library)
```

**Total: 4 SVG files across 4 folders**

---

## Index.html Navigation

```javascript
const wireframes = [
  { path: '01-viewer/viewer.svg', title: 'Viewer Interface' },
  { path: '02-workflow/workflow.svg', title: 'Workflow' },
  { path: '03-hero/hero.svg', title: 'Hero' },
  { path: '04-components/components.svg', title: 'Components' },
];
```

Navigation sections:
- 01 - Viewer
- 02 - Workflow
- 03 - Hero
- 04 - Components

---

## Acceptance Criteria

- [ ] Viewer wireframe shows the actual FirstFrame UI (sidebar, viewer, footer)
- [ ] Workflow wireframe shows Claude Code terminal + phase diagram
- [ ] Hero wireframe shows marketing messaging with film/storyboard metaphor
- [ ] Components wireframe documents standard patterns
- [ ] All wireframes follow the side-by-side Desktop|Mobile layout
- [ ] Marketing copy matches README.md messaging
- [ ] Viewer navigation updated with new wireframe paths

---

## Technical Notes

- Canvas: 1400x800 (standard)
- Theme: Dark (primary #8b5cf6, accent #d946ef)
- Desktop area: x=40, 900px wide
- Mobile area: x=980, 360x700 phone frame
- All SVGs must have explicit width/height attributes
