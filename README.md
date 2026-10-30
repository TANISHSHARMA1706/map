# CampusCompass Pro — beginner setup

This is a responsive web prototype for the LPU Design Thinking project “Where Is Block 34?”.

## Easiest way to try it (Windows)
1. Download and extract `CampusCompass_Pro.zip` (right-click → Extract All).
2. Open the extracted folder and double-click `index.html`.
3. The map and search may load, but **GPS and camera QR scanning generally need HTTPS or localhost**.
4. To run it correctly in VS Code:
   - Install Visual Studio Code if you do not have it.
   - Open VS Code → File → Open Folder → choose the extracted `CampusCompass_Pro` folder.
   - Click Extensions (four squares on the left), search `Live Server`, install the extension by Ritwick Dey.
   - Right-click `index.html` in the Explorer → **Open with Live Server**.
   - The browser should open a localhost address. Try GPS and QR there.
5. For mobile, publish the folder on an HTTPS static host (GitHub Pages or Netlify) and open that link on your phone.

## Features
- Responsive desktop/mobile layout
- Searchable saved campus places
- Live GPS position (after explicit permission) with accuracy circle
- Pedestrian route geometry using the public Valhalla / OpenStreetMap routing endpoint
- Fastest/shortest route preference, route distance and estimated time when the routing service responds
- Google Maps walking directions fallback
- QR scanner (camera permission) and QR generator for blocks 22, 28, 34, 37 and 38
- Scan a CampusCompass QR to identify the block and set it as the next route's starting point
- Copy route summary
- No app backend; location is processed in the browser and sent to the public routing service only when building a route

## Location accuracy and safety
- Public map references used: Block 34 approx 31.25162,75.70463; Block 38 approx 31.25207,75.70330; Block 28 approx 31.25311,75.70376; Block 37 / Central Library approx 31.25176,75.70404; LPU main campus approx 31.2533614,75.7035391; Cafe Chokolade approx 31.25788,75.70804.
- These are third-party map references, not an official Google Maps export. Verify exact entrances on-site before presenting the site as a dependable navigation service.
- Block 22 has no verified coordinate embedded. The site tries a live OpenStreetMap geocoding search instead of inventing a coordinate. If no result is returned, use Google Maps search and confirm the exact pin.
- The Shanti Devi Mittal Auditorium pin is approximate and must be verified.
- Route geometry follows available mapped paths. Campus-private paths may be missing, gated, or restricted; do not assume route safety/access. If routing fails, the app explicitly says it could not retrieve a pedestrian route and does not draw a fake straight line as a route.
- Route distance and time are only as accurate as map data, location accuracy and the public routing service. Shortest/fastest are routing-engine preferences, not a guarantee of campus-authorized paths.
- The page loads Leaflet, OpenStreetMap tiles, QR libraries and fonts from online CDNs, so internet is needed.
- Do not print or deploy a QR until the pin and block details have been confirmed with LPU staff or a reliable campus map.


## Polished visual update
This edition adds a refined visual layer: soft gradient page lighting, glass-like sticky header, richer orange gradient actions, smoother focus/hover states, elevated panels, improved map controls, and responsive spacing. The navigation logic and campus location caveats are unchanged.


## CampusCompass Ultimate — five-interface edition

### Five interfaces
1. **Home** — product overview and campus map preview.
2. **Navigate** — start point, destination, fastest/shortest preference, GPS, route summary, and external turn-by-turn navigation.
3. **Explore** — searchable campus destinations.
4. **QR Scan** — scan or manually enter a CampusCompass block QR; create downloadable QR codes for the demo.
5. **Saved** — save favorite places locally and show campus-help/accessibility reminders.

### Added features
- Blocks 55 and 56 added to destination search and QR IDs. Their exact coordinates are **not guessed**; the app tries a public map lookup and tells the user to verify the entrance.
- Save/remove favorite destinations in browser storage.
- Responsive bottom navigation on phones and top navigation on desktop.
- PWA manifest, app icon, and basic app-shell service worker so it can be installed from a suitable HTTPS/local development origin. Live GPS, map tiles, route lookup, QR camera scanning, and some external libraries still need internet and permissions.

### Run in VS Code
1. Extract the ZIP.
2. Open the inner `CampusCompass_Pro` folder in VS Code.
3. Run `index.html` with Live Server.
4. In Chrome/Edge, use the install icon or browser menu → **Install CampusCompass** if available.

### Accuracy and safety notes
Several map pins in this student prototype are approximate. Blocks 22, 55, and 56 use a lookup because their exact coordinates are unverified. Verify every building entrance and pedestrian path on-site with LPU information before a live demo. This is a navigation prototype, not an official campus map. The emergency/help panel intentionally directs users to official campus contacts instead of inventing phone numbers.
