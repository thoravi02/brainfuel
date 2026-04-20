# Brain Fuel

A content discovery tool for people thinking about product management, consulting, and venture capital. Curated editorial reading, daily/weekly feeds, quotes, and personal notes — all client-side, no backend.

Live site: _add your GitHub Pages URL here after enabling Pages_

## Stack

Single-file static site. `index.html` contains HTML, CSS, and vanilla JavaScript. No build step, no framework, no server.

- **Persistence:** `localStorage` in your browser. Your bookmarks, highlights, and notes stay on the device you saved them on.
- **Portability:** Export / Import JSON from inside the app to move data between devices.
- **Refresh:** RSS fetched via [rss2json](https://rss2json.com) (free, no key). Daily feeds refresh every 24h, weekly feeds every 7d, cached per browser.

## Deploy to GitHub Pages

1. Create a new public repo on GitHub — call it something like `brainfuel` or `brainfuel-site`.
2. Push this folder's contents to the repo root:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```
3. In the repo on GitHub: **Settings → Pages → Build and deployment**.
4. Under **Source**, pick **Deploy from a branch**.
5. Under **Branch**, pick `main` and folder `/ (root)`. Save.
6. Wait ~30–60 seconds. Your site will be live at:
   `https://YOUR-USERNAME.github.io/YOUR-REPO/`

Refresh once, add the URL to your phone's home screen, and you have a web app.

## Updating

Edit `index.html` locally, then:
```bash
git add index.html
git commit -m "Update content"
git push
```
GitHub Pages rebuilds automatically.

## Using it on your phone

iOS Safari: open the site → Share → **Add to Home Screen**.
Android Chrome: open the site → three-dot menu → **Add to Home screen**.

It opens like a native app, works offline after first load for the cached reads, and keeps your bookmarks per device.

## Syncing data across devices

Open the app on your primary device, open the top menu, choose **Export data**. Save the JSON. On a new device, open the app → **Import data** → pick that file. You're in sync.

## Privacy

No analytics. No cookies. No accounts. The site reads public RSS feeds through rss2json and stores your activity locally. The only network calls are to the feeds listed in `index.html` and `rss2json.com`.

## Custom domain (optional)

If you own a domain, you can point it at GitHub Pages: Settings → Pages → Custom domain. Add a `CNAME` file to the repo with your domain on one line. See [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
