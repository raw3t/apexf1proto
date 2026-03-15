# APEX F1

> The open-source F1 companion app — live races, standings, driver profiles, team history & more.

**Live demo:** `https://raw3t.github.io/apexf1proto`

---

## What is this?

APEX is a mobile-first web app for Formula 1 fans. It's designed to feel like a native app — install it on your phone's home screen and it works like an app (no App Store needed).

Features:
- Live race leaderboard with lap progress
- Countdown to next race
- Full driver profiles with career history
- Team details with history, chassis & engine info
- Complete 2025 race schedule (all 24 rounds)
- Driver & constructor standings
- Search and filter drivers by team
- Race results with full classification
- Works offline (PWA)

---

## How to put it on your phone

### iPhone (Safari)
1. Open the live site in **Safari**
2. Tap the **Share** button (box with arrow)
3. Tap **"Add to Home Screen"**
4. Tap **Add**

### Android (Chrome)
1. Open the live site in **Chrome**
2. Tap the **three dots** menu
3. Tap **"Add to Home Screen"** or **"Install App"**
4. Tap **Install**

---

## How to get it live (for the owner)

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up for a free account.

### Step 2 — Create a new repository
1. Click the **+** button in the top right
2. Click **New repository**
3. Name it `apexf1`
4. Make sure it's set to **Public**
5. Click **Create repository**

### Step 3 — Upload the files
1. On your new repository page, click **uploading an existing file**
2. Drag and drop ALL files from this folder:
   - `index.html`
   - `manifest.json`
   - `.github/` folder (the whole folder)
3. Scroll down and click **Commit changes**

### Step 4 — Turn on GitHub Pages
1. Go to your repository **Settings** (tab at the top)
2. Click **Pages** in the left sidebar
3. Under "Source", select **GitHub Actions**
4. That's it — your site will be live at `https://YOUR_USERNAME.github.io/apexf1` in about 2 minutes

### Step 5 — Check it's working
Go to the **Actions** tab in your repository. You should see a green checkmark next to your deploy. Click it to see the live URL.

---

## How to update data

All the race results, standings and driver data are in `index.html` inside the `<script>` tag. Look for:

```js
const drivers = [ ... ]   // driver standings & profiles
const teams   = [ ... ]   // team info
const races   = [ ... ]   // schedule & results
const liveData = [ ... ]  // live race leaderboard
```

To update after a race:
1. Open `index.html` in any text editor (Notepad, TextEdit, VS Code)
2. Find the race in the `races` array
3. Change `done: false` to `done: true`
4. Add `winner: 'Driver Name'` and `winnerTeam: 'Team Name'`
5. Fill in the `results` array with the full classification
6. Update `drivers` points and positions
7. Upload the updated file to GitHub (same as Step 3 above)

---

## Tech stack

| Thing | What it is |
|-------|-----------|
| HTML/CSS/JS | Single file, zero dependencies, zero build step |
| PWA | Works offline, installable on phone |
| GitHub Pages | Free hosting, auto-deploys on every push |
| GitHub Actions | CI/CD pipeline (the deploy.yml file) |

No Node.js. No npm. No React. No build step. Just one HTML file.

---

## Want to contribute?

Pull requests are welcome. Here are good first contributions:

- [ ] Hook up live data from [OpenF1 API](https://openf1.org) (free, no key needed)
- [ ] Add qualifying results to race detail pages
- [ ] Add fastest lap tracking
- [ ] Add circuit map / track layout per race
- [ ] Dark/light theme toggle
- [ ] Push notifications for race start
- [ ] Historical seasons (2024, 2023...)
- [ ] Driver head-to-head comparison

### How to contribute
1. Fork this repo (click **Fork** top right)
2. Make your changes
3. Open a Pull Request

---

## License

MIT — free to use, modify and distribute.

---

*Data is manually curated for the 2025 season. Not affiliated with Formula 1 or the FIA.*
