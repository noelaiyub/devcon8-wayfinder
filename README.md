# Devcon 8 Wayfinder (trial build)

Unofficial Level 3 wayfinder for Devcon 8, Jio World Centre, Mumbai.
Scan a QR code to set your position, then walk: the phone counts your steps and reads the compass, and your character moves on the 3D map.

## Files

- `index.html`: the whole site (map, schedule, friends, live tracking)
- `qr.html`: one QR code per spot on Level 3, for testing and printing

## Deploy on Vercel (same way as devcon8-id)

1. Create a new GitHub repo, for example `devcon8-wayfinder`.
2. Upload `index.html`, `qr.html` and this `README.md` to the repo root.
3. In Vercel: Add New → Project → import the repo → Deploy. There's no build step and no framework.
4. Open `https://<your-project>.vercel.app` on your phone.

Phone sensors and the camera only work on an **https** site, so test on the Vercel link, not on a file opened from your phone's storage.

## How to test at home

1. Open `https://<your-project>.vercel.app/qr.html` on your laptop.
2. Open the main site on your phone and tap **Scan QR**, then scan e.g. "Lifts (west)".
3. Tap **Start tracking** and allow Motion & Orientation (iPhone asks once).
4. Hold the phone in front of you, point it the way the orange arrow points, and tap **Align**.
5. Walk normally. Watch the Steps counter and the character move.
6. Scan another code (e.g. "Hub 3"). Your position snaps there, and after 10+ steps the step length gets tuned automatically.

If steps are missed, open **Fine-tune** and move Step sensitivity to the left. If extra steps are counted, move it right.
**Simulate a step** moves the character one step without walking, which is useful on a laptop.

## Limits

- Accuracy drifts by roughly 5–10 m per 100 m walked. Each QR scan resets it.
- Metal in large halls can disturb the compass. Tap **Align** again if the character walks the wrong way.
- Friend sharing (crews) only works inside claude.ai for now. On Vercel it needs a small realtime backend.
- The session schedule is sample data until the official programme is added.
