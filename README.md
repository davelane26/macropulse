# ⚡ MacroPulse — Daily Meal & Macro Calculator

> Precision, dark-mode-first daily nutrition calculator, food builder, and multi-day macro tracker with dual cloud synchronization (GitHub Gist & Firebase Realtime Database) and offline PWA support.

---

## 🚀 Live Demo & Mobile Access
Once deployed to GitHub Pages, access MacroPulse from your desktop browser or phone at:
```
https://<your-github-username>.github.io/macropulse/
```

### Install as Native App on Mobile (PWA)
MacroPulse includes embedded web manifest configuration and mobile viewport tags:
- **iPhone / iOS (Safari):** Tap the **Share** button (box with upward arrow) &rarr; Select **"Add to Home Screen"**.
- **Android (Chrome):** Tap the **Three Dots menu (⋮)** &rarr; Select **"Install app"** or **"Add to Home screen"**.
- Launches full-screen like a native app with zero address bar clutter and instant local caching!

---

## ✨ Core Features

### 1. Macro Architecture & Targets
- **Default Baseline:** 190g Protein, 250g Carbs, 70g Fat & 2,390 kcal (standard 4/4/9 kcal/g formula).
- **One-Click Presets:**
  - *High Protein / Resistance:* 190P / 250C / 70F (2,390 kcal)
  - *Balanced:* 160P / 220C / 75F (2,195 kcal)
  - *Cut / Lean:* 200P / 150C / 55F (1,895 kcal)
  - *Bulk / Surplus:* 200P / 350C / 90F (3,010 kcal)
- **Edit Targets Modal:** Interactive targets modal with live auto-calculating calories (`4*P + 4*C + 9*F`) or manual override.

### 2. Real-Time Dashboard
- **Consumed vs. Remaining Cards:** Live tracking for Calories, Protein, Carbs, and Fat with dynamic visual progress bars.
- **Caloric Energy Split Bar:** Multi-segment visualization of proportional caloric intake from Protein, Carbs, and Fat.

### 3. Categorized Meal Log
- **6 Meal Slots:**
  1. *Morning / Pre-Workout*
  2. *Post-Workout*
  3. *Breakfast*
  4. *Lunch*
  5. *Dinner*
  6. *Snacks & Extras*
- **Subtotals:** Running subtotal on each slot header (`P`, `C`, `F`, `kcal`).
- **Inline Multipliers:** Instant `-0.25x` and `+0.25x` portion scaling buttons on every logged item.
- **Delete Button:** Fast removal with confirmation toast.

### 4. Food Builder & Staples Library
- **28+ Pre-Loaded Staples:** Whole foods categorized into *High Protein*, *Carb Sources*, and *Healthy Fats* (Chicken Breast, Whey Isolate, Greek Yogurt, Eggs, Egg Whites, 93/7 Ground Beef, Salmon, Tuna, Oats, Jasmine Rice, Sweet Potato, Avocado, Almonds, Peanut Butter, Fairlife Core Power Elite, etc.).
- **Live Scaled Portion Preview:** Adjust portion slider (`0.5x` to `3.0x`) to see exact scaled macros and calories in real time before logging.
- **Custom Food Entry:** Log custom foods and optionally check **"Save to My Staples"** for one-click reuse in future days.

### 5. Multi-Day Calendar Navigation
- Top date bar with `◀ Previous Day`, HTML5 date picker, `Next Day ▶`, and `Today` quick jump.
- Historical days stored separately under `YYYY-MM-DD` index.
- **Copy Yesterday's Meals:** Quick-action banner shown when viewing an empty day to duplicate all meals from the prior day in one click.

### 6. Dual Cloud Sync Engine (`StorageSyncManager`)
- **Zero-Latency Local Fallback:** Read/write to `localStorage` immediately.
- **GitHub Gist Sync:**
  - Provide a GitHub Personal Access Token (`gist` scope).
  - Leave Gist ID blank on first sync to automatically generate a secret Gist containing `macropulse_state.json`.
  - Automatically pushes state changes after a 1.5s debounce.
  - Manual "Push to Cloud" and "Pull from Cloud" buttons.
- **Firebase Realtime Database Sync:**
  - Connect your Firebase RTDB URL (e.g. `https://your-project-default-rtdb.firebaseio.com`).
  - Supports Server-Sent Events (SSE) streaming so changes made on your phone update your PC browser in real time without refreshing.

### 7. Export & Backup
- **Export Day CSV:** Download clean spreadsheet of the active day's meal entries.
- **Export All History CSV:** Complete multi-day archive for spreadsheet tracking.
- **JSON Backup & Restore:** Complete backup file for safekeeping.

---

## 🛠️ GitHub Repository & Pages Setup

### 1. Initialize Git & Push to GitHub
Run the following in the project root:
```powershell
git init -b main
git add .
git commit -m "Initial commit: MacroPulse Daily Meal & Macro Calculator"
```

Create a new repository on [GitHub](https://github.com/new) named `macropulse`.

Link your remote and push:
```powershell
git remote add origin https://github.com/<your-username>/macropulse.git
git push -u origin main
```

### 2. Enable GitHub Pages
1. Go to your repository on GitHub: `https://github.com/<your-username>/macropulse`.
2. Click **Settings** &rarr; **Pages** (in the left sidebar).
3. Under **Build and deployment** &rarr; **Source**, select **GitHub Actions**.
4. The `.github/workflows/deploy.yml` workflow will automatically run and publish your app.
5. Your live URL will appear at: `https://<your-username>.github.io/macropulse/`
