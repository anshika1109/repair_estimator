# Spark Homes Repair Estimator

A mobile-first Progressive Web App (PWA) for estimating repair costs during property walkthroughs. Built for Spark Homes' acquisition team to quickly assess renovation costs on-site.

## Approach

The app is designed around the real workflow: an agent walks through a property room by room, checks off needed repairs, and gets a running cost total. The UI prioritizes speed and reliability in the field — large touch targets, section-by-section navigation with Previous/Next buttons, and offline-first architecture.

Key design decisions:
- **Section-based navigation** with horizontal tabs and Previous/Next buttons so agents work through rooms sequentially without losing their place
- **Tap-to-select line items** with quantity inputs — items are selectable cards, not buried in tables
- **Room flexibility** — add/remove bathroom, kitchen, bedroom, and living area instances to match any property layout
- **Notes with quick templates** — one-tap common observations (foundation issues, mold, etc.) to speed up documentation

## Libraries Used (CDN)

- **Tailwind CSS** — utility-first CSS framework for responsive layout
- **xlsx-js-style** — Excel file generation with cell styling (colored headers, formatted currency)
- **JSZip** — ZIP file creation for bundling Excel + photos on export

No build tools, no Node.js server, no framework dependencies.

## How to Run Locally

1. Clone this repo
2. Serve the files with any static server:
   ```bash
   python3 -m http.server 8080
   ```
3. Open http://localhost:8080 in your browser

Or simply open `index.html` directly in a browser (service worker requires HTTP server for full offline support).

## Features

- ✅ Multi-project management (create, rename, delete, switch)
- ✅ 75+ repair line items from official price list
- ✅ 19 collapsible groups across 5 sections
- ✅ Adjustable rooms (add/remove Bathroom, Kitchen, Bedroom, Living areas)
- ✅ "No Action Needed" per group
- ✅ Running cost total (sticky header)
- ✅ Progress bar (group-based completion tracking)
- ✅ Photo capture with compression
- ✅ Project notes with quick-note templates
- ✅ Global price CSV upload + per-project price overrides
- ✅ Custom line items (add/remove per group)
- ✅ Styled Excel export in ZIP with photos
- ✅ Deal Analyzer (70% rule, ROI, profit projection)
- ✅ Project Comparison (side-by-side cost/profit analysis)
- ✅ PWA with service worker (offline support)
- ✅ Installable on Android and iOS

## Creative Additions

1. **Project Comparison** — Side-by-side table comparing all properties by repair cost, ARV, max offer (70% rule), and projected profit. Sorted by best deal. Helps agents prioritize which properties to pursue when evaluating multiple leads.

2. **Deal Analyzer** — Enter ARV and purchase price to instantly see profit margin, ROI, and whether the deal passes the 70% rule. Replaces back-of-napkin math with real-time calculations.

## File Structure

```
index.html      — Complete application (single file)
sw.js           — Service worker for offline caching
manifest.json   — PWA manifest for installation
icon-192.png    — App icon (192x192)
icon-512.png    — App icon (512x512)
```
