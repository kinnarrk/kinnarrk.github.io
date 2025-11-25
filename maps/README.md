# H3 Hexagon Selector

A simple prototype app for selecting H3 hexagons on Google Maps.

## Setup

1. Get a Google Maps API key:
   - Go to https://console.cloud.google.com/
   - Create a new project or select existing one
   - Enable "Maps JavaScript API"
   - Create credentials (API key)

2. Update `index.html`:
   - Replace `YOUR_API_KEY_HERE` with your actual Google Maps API key

## Usage

1. Open `index.html` in your web browser
2. The map will load centered on San Francisco with hexagons
3. **Select a zone** by clicking one of the three zone buttons (Blue, Green, or Orange)
4. **Click hexagons** to toggle them in the active zone (they'll change to that zone's color)
5. **Hold Ctrl (or Cmd on Mac) and drag** across multiple hexagons to select them quickly
6. **Normal drag** (without Ctrl/Cmd) pans the map
7. Selected hexagon IDs appear at the bottom in three columns, one per zone
8. Click on hexagon IDs to copy them to clipboard
9. Use the "H3 Resolution" control to change hexagon size (0-15)
10. Click "Redraw Hexagons" to update the grid (hexagons auto-redraw when you zoom)
11. Use "Search Location" with autocomplete - start typing and select from suggestions
12. Click "Clear All Zones" to remove all zone assignments

## Features

- **Multi-zone selection** - Organize hexagons into 3 color-coded zones (Blue, Green, Orange)
- **Ctrl+Drag selection** - Hold Ctrl/Cmd and drag to select multiple hexagons in one motion
- **Smart map interaction** - Normal drag pans the map, Ctrl+drag selects hexagons
- Interactive hexagon selection on Google Maps
- **Complete map coverage** - No gaps between hexagons using H3's `polygonToCells`
- **Map overlays** - Toggle transit routes and POI (airports, hotels, etc.)
- Adjustable H3 resolution (0-15)
- Display hexagon IDs in three columns (one per zone) with matching colors and aligned layout
- Click to copy hexagon IDs to clipboard
- **Location search with autocomplete** - Jump to any location with intelligent suggestions as you type
- Clean, modern UI with intuitive controls
- No build process or framework needed
- Uses H3 v4.1.0 from CDN
- Dynamic hexagon rendering - automatically redraws when you pan or zoom the map
- Reassign hexagons between zones

## Controls

### Map Overlays
- **Transit Routes**: Show public transportation lines and stations
- **POI (Hotels, Airports, etc.)**: Show points of interest including hotels, airports, restaurants, etc. (enabled by default)

### Zone Selection
- **Zone 1 (Blue)**: Select this zone to assign hexagons to Zone 1
- **Zone 2 (Green)**: Select this zone to assign hexagons to Zone 2
- **Zone 3 (Orange)**: Select this zone to assign hexagons to Zone 3

### Other Controls
- **H3 Resolution**: Controls the size of hexagons (0-15, higher = smaller hexagons)
- **Redraw Hexagons**: Regenerates hexagons at current resolution
- **Clear All Zones**: Removes all zone assignments from all hexagons
- **Search Location**: Start typing and select from autocomplete suggestions, or enter manually and click "Go"

### How Zones Work

1. Click a zone button to make it active (it will show a checkmark)
2. **Click** a single hexagon to toggle it in the active zone:
   - If unselected or in a different zone → assigns to active zone
   - If already in active zone → deselects it
3. **Hold Ctrl (Cmd on Mac) + Drag** across multiple hexagons to toggle them in one motion
4. Hexagons change color to match their zone as you select them
5. You can switch between zones and reassign hexagons to different zones
6. All hexagon IDs are displayed at the bottom in three columns (one per zone), aligned with the zone buttons above

**Selection Methods:** 
- **Normal click** - Toggle individual hexagons (no Ctrl/Cmd needed)
- **Ctrl/Cmd + Drag** - Select multiple hexagons quickly while preventing map pan
- **Normal drag** (without Ctrl/Cmd) - Pans the map normally

**Tips:** 
- Click over already-selected hexagons to deselect them
- Use Ctrl/Cmd + drag for fast area selection
- Use different zones to organize different areas
- **Zoom level**: Hexagons only display at zoom level 11 or higher to prevent performance issues

## Libraries Used

- H3-js v4.1.0 (from unpkg CDN)
- Google Maps JavaScript API

