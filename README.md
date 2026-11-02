# Indoor QR + Phone Motion Test

A zero-dependency, static HTML prototype of QR checkpoint positioning and phone-motion step estimation, designed for GitHub Pages.

## Publish on GitHub Pages
1. Create a public GitHub repository (e.g. `indoor-qr-pdr`).
2. Upload `index.html` and `README.md` at the repository root.
3. Open **Settings → Pages**, select **Deploy from a branch**, choose **main** and **/(root)**, then save.
4. Open `https://YOUR_USERNAME.github.io/indoor-qr-pdr/` on a smartphone.
5. Tap **Enable motion sensors** (grant permission if prompted), select a checkpoint, then **Start tracking**.
6. Walk along a straight corridor holding the phone upright, pointing in the walking direction. Watch estimated steps and blue-dot movement.
7. Open checkpoint URLs using your phone camera or the in-app scanner (only if the browser supports BarcodeDetector).

## Checkpoint URL examples
- `https://YOUR_USERNAME.github.io/indoor-qr-pdr/?point=ENTRANCE`
- `https://YOUR_USERNAME.github.io/indoor-qr-pdr/?point=JUNCTION`
- `https://YOUR_USERNAME.github.io/indoor-qr-pdr/?point=LIFT`

Generate printable QR codes from those URLs using any QR generator. The in-app scanner uses BarcodeDetector, which is not supported in every browser. The default phone camera can open the URL instead.

## What is and isn't implemented
- Yes: sample floor plan, checkpoints, URL-based QR positioning, optional camera QR reader, motion/orientation permission, basic accelerometer threshold step counting, approximate heading, blue-dot simulation, manual checkpoint correction.
- No: reliable walking-direction tracking, accurate indoor localization, true multi-floor detection, sensor fusion, real 2D routing, automatic drift correction, calibration, or background motion tracking.
- Step length is fixed at 0.7m and map scale at 20 pixels/m. Estimated movement is constrained to a single horizontal corridor.
- Heading conventions vary by browser and device; direction estimates may be wrong. If they are wrong, test the simulation controls instead.
- Sensor APIs need HTTPS and browser support. Desktop browsers often have no sensors. iOS may ask for motion permission after a tap.
- Motion processing is local; nothing is sent to a server.

**Safety:** This is a proof of concept. Never use it for emergency or clinical wayfinding.
