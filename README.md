# 🐕 Dog Walk Planner

A PWA that recommends the best times to walk your dogs based on live local weather — factoring in rain, temperature safety, wind, and daylight hours.

## Features

- 📍 **Location via GPS or postcode** — auto-detect or type a UK postcode
- 🌤️ **Live weather** from Open-Meteo (free, no API key needed)
- 🏆 **Scored walk windows** — top 3 slots ranked by rain, temp, wind, and daylight
- 📊 **Day-at-a-glance chart** — visual 24-hour overview
- 📅 **3-day forecast** — Today, Tomorrow, and the day after
- 🌡️ **Dog safety limits** — warns above 25°C (paw burn risk) and below -5°C
- 📱 **Installable PWA** — add to home screen on iOS and Android

## Deploy to GitHub Pages

1. Create a new repository (e.g. `dog-walk-planner`)
2. Upload all files keeping the folder structure:
   ```
   index.html
   manifest.json
   sw.js
   icons/
     icon-192.png
     icon-512.png
   ```
3. Go to **Settings → Pages → Source: Deploy from branch → main / (root)**
4. Your app will be live at `https://yourusername.github.io/dog-walk-planner/`

## Install as PWA

**Android (Chrome):** Open the URL → tap the three-dot menu → "Add to Home screen"  
**iOS (Safari):** Open the URL → tap Share → "Add to Home Screen"

## How scoring works

Each hour is scored 0–100% based on:
| Factor | Weight |
|---|---|
| Heavy rain | −96% |
| Moderate rain | −82% |
| Light rain | −60% |
| Temperature > 25°C | −95% (unsafe) |
| Temperature < −5°C | −95% (unsafe) |
| Night-time | −75% |
| Strong wind >50 km/h | −60% |

The top 3 remaining hours become your recommended walk windows.

## APIs used

- [Open-Meteo](https://open-meteo.com/) — weather forecasts (free, no key)
- [Postcodes.io](https://postcodes.io/) — UK postcode lookup (free, no key)
