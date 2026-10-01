# Alert - Fish Disease Early Warning System
Installable mobile web app (PWA): live water-quality monitoring, 4-level alerts, disease risk hints, cameras, GPS map, and one-tap service requests (WhatsApp/SMS) to +233547636057.

## Deploy on GitHub Pages
1. Create a repo, upload these files (index.html, manifest.webmanifest, sw.js, icon.svg).
2. Settings > Pages > Deploy from branch > main / root.
3. Open the https URL on your phone > browser menu > "Add to Home screen".

## Connect sensors
Make your ESP32/Arduino gateway serve JSON at a URL (CORS enabled):
`{"temp":28.1,"ph":7.4,"do":5.8,"nh3":0.2,"turb":22}`
Paste the URL in Settings. Note: a https GitHub page can only read https feeds (use a tunnel or HTTPS gateway). Empty = demo data.

## Cameras
Add MJPEG or snapshot URLs (same https note applies). The phone camera also works.

## Alert levels
1 Normal, 2 Watch (one parameter off), 3 Warning (2+ off), 4 Critical (any parameter in danger range). Thresholds are in `T` in index.html (tuned for warm-water fish like tilapia/catfish; adjust to your species).

## Diagnostics
The Diagnose tab lets the farmer tick observed signs (gasping, white spots, sores, etc.) and mortality level. These are scored against live water readings to rank likely conditions (hypoxia, ammonia toxicity, columnaris, Aeromonas, Streptococcus, ich, fungus, gill parasites). Every service request automatically includes symptoms, mortality, suspected diagnosis, readings and GPS location. Rules live in `DX` in index.html. Preliminary guide only; confirm with a vet or lab.

## Install on phone
Open the GitHub Pages link in Chrome on Android, tap the **Install app** button in the app header (or Chrome menu > Install app). Requires https, which GitHub Pages provides.
