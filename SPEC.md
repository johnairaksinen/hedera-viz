# Hedera Visualization — Spec

Build a single-page web visualization of "Julius Hedera" — a multi-agent system visualized as ivy (murgröna/hedera). The page should be beautiful, organic, and alive.

## Concept

Julius Hedera is the hub agent. From it grow "slingor" (tendrils) — specialized narrow agents. The visualization should feel like a living plant: the hub is the root/trunk, and each slinga grows outward as a vine tendril with leaves.

## Architecture

Single `index.html` with inline CSS + JS. No build step. Use Canvas or SVG for the vine rendering. Keep it deployable as a static file.

## Visual Design

### Overall
- **Background:** Very dark (#0a0a0a), almost black
- **Color palette:** Deep greens (#1a4a1a → #2d7a2d → #4aad4a), gold accents (#c8a44e) for highlights
- **Font:** System serif for headings, system sans for data
- **Mood:** Organic, bioluminescent, alive. Think dark forest with glowing vines.

### The Plant
- **Center/root:** Julius Hedera hub — a glowing golden node with the ❧ symbol
- **Tendrils:** Organic curved lines (use bezier curves) growing outward from the center
- **Each tendril = one slinga** — ends in a cluster of leaves
- **Leaves = skills** — small leaf shapes along each tendril, with skill names
- **Subtle animation:** Gentle swaying/breathing. Leaves slightly pulse. New growth feels alive.

### Layout
- Julius Hedera in the center
- 4 slingor radiating outward (like compass directions, but organic — not perfectly symmetric):
  1. 🧸 Pappaslingan (family/) — warm tones
  2. 🌿 Styrelseslingan (board/) — classic green
  3. 🩺 Hälsoslingan (health/) — blue-green tones
  4. ❧ Julius Hedera itself (main workspace) — gold/green

### Interaction
- **Hover on a tendril/node:** Expand to show skills list + data summary
- **Click on a slinga:** Shows detail panel with:
  - Agent name + emoji
  - Workspace path
  - List of skills (from AGENTS.md)
  - Data files (what's in the workspace)
  - Status/last activity if available

### Data Panel (when clicking)
A side panel or overlay that shows structured info about the selected agent. Clean, readable, dark-themed.

## Agent Data to Visualize

### Julius Hedera (main) ❧
- **Emoji:** ❧
- **Workspace:** ~/.openclaw/workspace
- **Skills:** morning-brief, gratitude-journal, provenance, music-log, content-ideas, book-interview, meeting-feedback, salon-audio, inspiration-objects, health-diary, haircut-booking, remotion-video, weather, github, coding-agent, imsg
- **Data:** MEMORY.md, SOUL.md, CONSTITUTION.md, knowledge/, memory/, drafts/
- **Role:** Hub agent. Talks to John. Weaves threads from all slingor.

### Styrelseslingan 🌿
- **Emoji:** 🌿
- **Workspace:** ~/.openclaw/workspace/board
- **Skills:** Mejlbevakning, Mötesförberedelse, Informationsbrev, Dokumentsammanfattning, Beslutsdokumentation, Kalkylverktyg, Påminnelser
- **Data:** meetings/, templates/, informationsbrev/
- **Role:** BRF Ekbacksskolan board work

### Hälsoslingan 🩺
- **Emoji:** 🩺
- **Workspace:** ~/.openclaw/workspace/health
- **Skills:** (health tracking, symptom logging, doctor visit prep)
- **Data:** (health diary, lab results)
- **Role:** John's health management (hyperakusis, eksem)

### Pappaslingan 🧸
- **Emoji:** 🧸
- **Workspace:** ~/.openclaw/workspace/family
- **Skills:** Kompiskartan, Aktiviteter & schema, Utvecklingslogg, Föräldranätverk, Presentidéer & önskelistor, Familjeplanering, Påminnelser
- **Data:** friends/, parent-friends/
- **Role:** John's role as father, Ester's development

## Technical Notes

- Use requestAnimationFrame for animation
- Bezier curves for organic vine paths
- Small random variation in leaf positions/sizes for natural feel
- Performance: keep it smooth on mobile too
- Responsive: works on phone and desktop
- No external dependencies — pure vanilla JS + Canvas/SVG

## Title
"Julius Hedera — Living Architecture"
Subtitle: "A multi-agent system, growing."
