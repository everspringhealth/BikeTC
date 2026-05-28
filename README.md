# Bike TC — bike.tc

A simple, fast, single-page biking resource for the Twin Cities. No build step, no
framework, no dependencies — just one `index.html`. Hosted free on GitHub Pages,
pointed at the premium domain **bike.tc**. Brought to you by Everspring Health.

## What's in here
- `index.html` — the whole site (HTML, CSS, JS, and the logo all in one file)
- `CNAME` — tells GitHub Pages to serve the site at `bike.tc`
- `README.md` — this file

## Put it live (about 15 minutes)

### 1. Create the repo
1. Make a new **public** GitHub repository (any name, e.g. `bike-tc`).
2. Upload `index.html` and `CNAME` to the root of the repo (drag-and-drop in the
   GitHub web UI is fine).

### 2. Turn on GitHub Pages
1. Repo → **Settings** → **Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Save.
4. In a minute or two it will publish at `https://<your-username>.github.io/<repo>/`.
   Confirm it loads before doing DNS.

### 3. Point bike.tc at it
1. Settings → Pages → **Custom domain**, enter `bike.tc`, Save. (This regenerates the
   `CNAME` file — that's expected.)
2. At your domain registrar (wherever you bought bike.tc), set DNS:

   **For the apex domain `bike.tc`** — create four **A** records pointing to GitHub Pages:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   (Optional, recommended) add the matching **AAAA** (IPv6) records:
   ```
   2606:50c0:8000::153
   2606:50c0:8001::153
   2606:50c0:8002::153
   2606:50c0:8003::153
   ```
   **For `www.bike.tc`** (optional) — a **CNAME** record to `<your-username>.github.io`.

   > These are GitHub's published Pages IPs. They rarely change, but confirm against
   > the current values in GitHub's docs ("Managing a custom domain for your GitHub
   > Pages site") before you save, just in case.

3. DNS can take anywhere from a few minutes to a few hours to propagate.
4. Back in Settings → Pages, once the domain check passes, tick **Enforce HTTPS**.

That's it — `https://bike.tc` is live.

## Editing
Everything is in `index.html`. To add a trail, destination, or resource, copy one of the
existing `.card` or `.lnk` blocks and edit the text. To swap in the real BikeTC logo,
replace the inline `<svg class="logo">…</svg>` blocks (there are three — nav, hero, footer)
with your artwork, or drop in an `<img>`.

## Notes
- The logo here is a clean SVG interpretation of the original BikeTC mark (the "e" and
  "c" as bike wheels, the "T" as handlebars). When you find a higher-res version of the
  real logo, it can be vectorized and dropped in.
- Content (trails, the 2023 Minnesota stop-as-yield law, the post–Nice Ride bike-share
  setup) was current as of May 2026. The resource links point to official city/state
  pages that maintain the source of truth, so the site stays accurate even as details change.
