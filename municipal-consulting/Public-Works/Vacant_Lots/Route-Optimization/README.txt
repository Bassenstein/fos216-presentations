FOS·GIS — Vacant Lot Route Optimizer
Cuyahoga County | Northeast Ohio Municipal Consulting
=====================================================

FILES IN THIS PACKAGE
---------------------
  FOS_GIS_Route_Optimizer.html  — Main app file
  manifest.json                  — PWA install manifest
  sw.js                          — Service worker (offline caching)
  README.txt                     — This file

HOW TO DEPLOY (all three files must be in the same folder)
----------------------------------------------------------

OPTION A — Local use (single device, no server)
  1. Copy all 3 files to a folder on your device
  2. Open FOS_GIS_Route_Optimizer.html in Chrome or Edge
  3. Works immediately. Photos stored in browser IndexedDB.
  Note: PWA install and offline mode require a server (Option B or C).

OPTION B — Tablet/field use via local network (recommended for crews)
  1. Copy all 3 files to a folder on a Windows PC or laptop
  2. Run a simple local server:
       Windows: Open PowerShell in the folder, run:
         python -m http.server 8080
       Mac/Linux:
         python3 -m http.server 8080
  3. Find your PC's local IP (e.g. 192.168.1.10)
  4. On each tablet, open Chrome and go to:
       http://192.168.1.10:8080/FOS_GIS_Route_Optimizer.html
  5. Chrome will show "Add to Home Screen" — tap it to install
  6. App icon appears on tablet home screen. Works offline after first load.

OPTION C — Web hosting (best for multi-device sync)
  1. Upload all 3 files to any web host (Netlify, Vercel, city server, etc.)
  2. Share the URL with all crew tablets and supervisor desktops
  3. Crew members open URL in Chrome → "Add to Home Screen" to install
  4. iOS (iPad/Safari): Share button → "Add to Home Screen"
  Note: For cross-device photo sync, a Supabase backend is required (separate build).

INSTALL ON TABLET
-----------------
  Android (Chrome):
    - Open the app URL in Chrome
    - Tap the 3-dot menu → "Add to Home Screen" OR
    - Wait for the install banner at the bottom of the screen

  iPad/iPhone (Safari):
    - Open the app URL in Safari
    - Tap the Share button (box with arrow)
    - Tap "Add to Home Screen"
    - The app installs with the FOS·GIS icon

OFFLINE BEHAVIOR
----------------
  - Map tiles are cached after first load — maps work offline
  - All lot data, routes, and crew data stored in browser
  - Photos stored in IndexedDB — survive browser close, offline-safe
  - Orange "OFFLINE MODE" bar shows at top when connection is lost

NEXT STEPS — Supabase Cloud Sync
---------------------------------
  To enable real-time photo sync between field crews and supervisors:
  1. Create a free account at supabase.com
  2. Share your project URL and anon key
  3. We build the synced version with:
       - Central lot/route/crew database
       - Photo storage bucket (crews upload, supervisors review)
       - Role-based access (crew vs supervisor)
       - Live dashboard for supervisor oversight

SUPPORT
-------
  Built by FOS 216 for Cuyahoga County municipal operations.
  For questions or customization: contact your FOS 216 consultant.
