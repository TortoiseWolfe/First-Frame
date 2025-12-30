# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **planning template** for projects using the SpecKit workflow. It contains:
- Feature specifications
- SVG wireframes with interactive viewer
- Project constitution template

## Commands

### Wireframe Viewer Development

```bash
cd docs/design/wireframes
npm install                      # Install dependencies
npm run dev                      # Start dev server with hot reload
npm test                         # Run Playwright tests
npx playwright install chromium  # Install browser (first time)
```

### Features vs Specs

- **Feature** = The idea (natural language description of what you want to build)
- **Spec** = Structured requirements derived from the feature via `/specify`

### SpecKit Workflow (extends GitHub SpecKit)

**Phase 1: Vision & Design**
```bash
/speckit.specify        # Create spec from feature description
/speckit.clarify        # Refine requirements
/wireframe              # Generate dark theme SVG wireframes (1400x800)
/wireframe-light        # Generate light theme SVG wireframes
# ⛔ HARD STOP - Review wireframes with stakeholders before proceeding
```

**Phase 2: Implementation**
```bash
/speckit.plan           # Design implementation approach
/speckit.checklist      # Generate implementation checklist
/speckit.tasks          # Generate task list
/speckit.taskstoissues  # Convert tasks to GitHub issues
/speckit.analyze        # Review spec quality
/speckit.implement      # Execute implementation plan
```

### Wireframe Viewer Commands

```bash
/hot-reload-viewer      # Start wireframe viewer at localhost:3000
/svg-to-png             # Convert SVG wireframes to PNG (1200x800)
```

## Browser Testing with MCP Toolkit

Use the MCP Docker Playwright tools for browser testing (not local Playwright):
- `mcp__MCP_DOCKER__browser_navigate` - Navigate to URL (use `host.docker.internal` for localhost)
- `mcp__MCP_DOCKER__browser_snapshot` - Get page accessibility tree
- `mcp__MCP_DOCKER__browser_take_screenshot` - Capture screenshots
- `mcp__MCP_DOCKER__browser_click` - Click elements
- `mcp__MCP_DOCKER__browser_press_key` - Simulate keyboard input

Example: To test the wireframe viewer running on localhost:3000:
```
mcp__MCP_DOCKER__browser_navigate url="http://host.docker.internal:3000"
```

## Wireframe Viewer Keyboard Shortcuts

- **F**: Toggle focus mode (hide sidebar/footer), **Escape** to exit
- **Left/Right**: Previous/Next wireframe
- **Up/Down**: Zoom in/out
- **+/-**: Zoom in/out
- **0**: Reset zoom to 85%

## Generating Wireframes

Use `/wireframe` (dark theme) or `/wireframe-light` (light theme) to generate SVGs from specs:

1. Reads the spec to understand the feature
2. Creates **side-by-side** wireframes (Desktop left, Mobile right) - default **1400×800**, expandable for complex features
3. Saves SVGs to `docs/design/wireframes/[feature-folder]/`
4. Updates `index.html` navigation (wireframes array + nav section)

### SVG Canvas Sizes
- **Standard**: 1400×800 (default)
- **Wide**: 1600×800 (extra annotation margins)
- **Tall**: 1400×1000 (complex vertical layouts)
- **Extended**: 1600×1000 (full annotation mode)

### SVG Layout Dimensions
- **Desktop area**: x=40, y=60, 900px wide (3-column: 200 sidebar | 440 main | 240 detail)
- **Mobile area**: x=980, y=60, 360×700 phone frame
- For wide canvas (1600): shift Desktop to x=140, Mobile to x=1080

### SVG Dark Theme Colors
- Background: gradient `#0f172a` to `#1e293b`
- Primary: `#8b5cf6` (violet)
- Accent: `#d946ef` (fuchsia)
- Panels: `#1e293b`, `#334155`
- Borders: `#475569`
- Text: `#fff` (headings), `#94a3b8`/`#cbd5e1` (body), `#64748b` (muted)

## Implementation Options

When ready to build:

**Option A**: Fork [ScriptHammer.com](https://scripthammer.com) - Next.js 15, React 19, Supabase, Tailwind

**Option B**: Stay in FirstFrame - use `/speckit.plan`, `/speckit.tasks`, `/speckit.implement`
