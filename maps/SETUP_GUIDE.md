# Quick Setup Guide - Getting Your Google Maps API Key

## Step-by-Step Instructions

### 1. Go to Google Cloud Console
Visit: https://console.cloud.google.com/

### 2. Create or Select a Project
- Click on the project dropdown at the top
- Click "New Project" or select an existing one
- Give it a name like "H3 Test App"

### 3. Enable Maps JavaScript API
- In the left sidebar, go to **APIs & Services → Library**
- Search for "Maps JavaScript API"
- Click on it and press **"Enable"**

### 4. Create API Credentials
- Go to **APIs & Services → Credentials**
- Click **"Create Credentials"** button at the top
- Select **"API Key"**
- Your API key will be generated and displayed

### 5. (Optional) Restrict Your API Key
For security, you can restrict your API key:
- Click on the key name to edit it
- Under "Application restrictions", select "HTTP referrers"
- Add `file:///*` for local testing
- Under "API restrictions", select "Restrict key"
- Choose "Maps JavaScript API" only

### 6. Update index.html
- Open `index.html` in any text editor (VS Code, Sublime, TextEdit, etc.)
- Find line 156 (search for `YOUR_API_KEY_HERE`)
- Replace it with your actual API key

**Before:**
```html
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY_HERE&callback=initMap" async defer></script>
```

**After:**
```html
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyA1B2C3D4E5F6G7H8I9J0K1L2M3N4O5P6Q&callback=initMap" async defer></script>
```
(Use your actual key, not this example)

### 7. Enable Billing (if needed)
Google Maps requires billing to be enabled, but provides:
- **$200 free credit per month**
- You won't be charged unless you exceed this limit
- For this small test app, you'll likely stay well within free tier

To enable billing:
- Go to **Billing** in the left sidebar
- Link a billing account (or create one)
- Add payment method

### 8. Open the App
- Save `index.html`
- Double-click the file or open it in your web browser
- You should now see the map with hexagons!

## Troubleshooting

### "This page didn't load Google Maps correctly"
- Make sure you replaced `YOUR_API_KEY_HERE` with your actual key
- Check that billing is enabled
- Verify "Maps JavaScript API" is enabled

### Hexagons not showing
- Check browser console (F12) for errors
- Make sure H3.js library is loading (check Network tab)
- Try zooming in/out or panning the map

### Can't select hexagons
- Make sure the map has fully loaded
- Try clicking on the red hexagon outlines

## Quick Test
Once set up, you should see:
1. A map centered on San Francisco
2. Red hexagons covering the visible area
3. Ability to click hexagons (they turn blue)
4. Selected hexagon IDs appear at the bottom
5. Click IDs to copy them to clipboard

## Need Help?
- Google Maps API Documentation: https://developers.google.com/maps/documentation/javascript
- H3 Documentation: https://h3geo.org/

