# Parity Pricing

**Developed by Wes W. Gentry, Ph.D.**

A standalone feedstuff parity‑pricing tool. Choose 2–3 reference feedstuffs and an equal number of nutrients, enter prices and composition, and the app solves for the implied value of each nutrient — then prices your test feeds on both a dry‑matter and an as‑fed basis.

It runs entirely in the browser. No server, no data leaves the phone, no internet connection required after the page loads once.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire application (HTML, CSS, and JavaScript in one file). |
| `manifest.json` | Lets Android/Chrome install it to the home screen with the proper name and icon. |
| `icons/icon.svg` | Master vector icon. |
| `icons/apple-touch-icon.png` | 180 px icon iOS uses for *Add to Home Screen*. |
| `icons/icon-192.png`, `icon-512.png` | PWA icons for Android. |
| `icons/icon-1024.png` | Master raster icon (App Store size, if ever needed). |
| `icons/favicon-32.png` | Browser‑tab icon. |

---

## Hosting it free on GitHub Pages

1. **Create a repository.** On GitHub, click **New repository**. Name it whatever you like (for example `parity-pricing`). Make it **Public**. Do **not** add a README from GitHub — you already have one.

2. **Upload these files.** On the new repo page, click **Add file → Upload files**, then drag in `index.html`, `manifest.json`, `README.md`, and the whole `icons` folder. Keep the same folder layout (the `icons` folder stays a folder). Commit the changes.

3. **Turn on Pages.** Go to **Settings → Pages**. Under *Build and deployment → Source*, choose **Deploy from a branch**. Set the branch to **main** and the folder to **/ (root)**. Click **Save**.

4. **Wait ~1 minute, then visit your site.** GitHub will show a URL like:
   ```
   https://YOUR-USERNAME.github.io/parity-pricing/
   ```
   Open that on your phone.

---

## Putting it on your iPhone home screen

1. Open the GitHub Pages URL above **in Safari** (not the in‑app browser inside Mail or Files — those force dark mode and can make text hard to read).
2. Tap the **Share** button (the square with the up arrow).
3. Tap **Add to Home Screen**.
4. The balance‑scale icon and the name *Parity Pricing* will appear. Tap **Add**.

It now launches full‑screen like a native app, and works offline.

> **Android:** open the URL in Chrome, tap the **⋮** menu, and choose **Add to Home screen** / **Install app**.

---

## How to use the app

1. **Setup** — pick whether you want **2** or **3** reference feeds and nutrients. The two counts must match (a square system has exactly one solution).
2. **Reference feedstuffs** — choose each feed from the dropdown to load editable book values, type over any value you want, and enter the **listed price in $/ton as‑fed**.
3. **Valuation nutrients** — pick the nutrients (Protein, NEg, Fat, Roughage DM). Each can only be chosen once.
4. **Test feedstuffs** — enter the DM% and the selected‑nutrient composition for up to three feeds you want to value.
5. Tap **Calculate Parity**.

**Results show:**
- A **fit rating** (Ideal → Poor) based on how nutritionally distinct your reference feeds are, with a note on how to improve a weak fit.
- **Nutrient Regression Estimates** — the implied dollar value of each nutrient, with a friendly per‑lb or per‑Mcal figure.
- **Parity prices** for each test feed, shown both **$/ton DM** and **$/ton as‑fed**.

All nutrient inputs are on a **dry‑matter basis**; DM% is used to convert to as‑fed. NE values are in **Mcal/cwt**.

---

## Notes

- *Value is determined simply based on nutrient content. Inclusion and nutrient constraints of the ration will ultimately determine ingredient value.*
- Reference composition values are editable starting points; replace them with your own analyses for the most accurate results.

---

## Editing later

Everything is in `index.html`. Open it in any text editor. To change reference‑feed default values, look for the `FEEDS` array near the top of the `<script>` block. To change which nutrients are selectable, edit the `NUTRIENTS` array just above it.
