# J Harmony — Corporate Website

Static single-page site for **j-harmony.com** (Anti-Aging, Aesthetics, Wellness — A Proactive Medical Care Club), built for GitHub Pages hosting.

## Structure
- `index.html` — entire site (HTML + CSS + minimal JS, no build step, no dependencies beyond Google Fonts)
- `CNAME` — custom domain binding for GitHub Pages

## Deploy (GitHub Desktop workflow)
1. Create a new GitHub repo (e.g. `j-harmony-site`), clone it with GitHub Desktop.
2. Copy `index.html`, `CNAME`, and `README.md` into the repo folder.
3. Commit and push to `main`.
4. In the repo: **Settings → Pages → Source: Deploy from a branch → main / (root)**.
5. In **Settings → Pages → Custom domain**, confirm `j-harmony.com` is set (the CNAME file pre-seeds this) and check **Enforce HTTPS** once the cert issues.

## DNS cutover
At the domain registrar for j-harmony.com:
- **Apex (`j-harmony.com`)** — A records to GitHub Pages IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (plus optional AAAA: `2606:50c0:8000::153` … `8003::153`)
- **`www`** — CNAME record to `<github-username>.github.io`
- Remove/replace the old site-builder A/CNAME records. Keep MX records untouched so info@j-harmony.com mail keeps flowing.

Allow up to 24h for DNS propagation and the automatic Let's Encrypt certificate.
