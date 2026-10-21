# Sortwick website

Plain static files, no build step, no scripts, no cookies, no trackers.

`privacy/index.html` and `terms/index.html` are generated from `docs/legal/*.md` in the game repo by `scripts/build-website.sh`. Edit the markdown, run the script, commit. Do not edit those two pages by hand.

## Option A: Hostinger (simplest)
1. hPanel > Websites > your sortwick.com site > File Manager > `public_html`.
2. Upload the contents of this folder (not the folder itself): `index.html`, `style.css`, `icon.png`, `apple-touch-icon.png`, `img/`, `privacy/`, `terms/`, `support/`. Or zip the contents, upload the zip and use Extract.
3. Check https://sortwick.com/privacy/ , /terms/ and /support/ (also without the trailing slash).
`CNAME` and this README are not needed there.

## Option B: GitHub Pages
The game repo itself must stay private. Publish only this folder from a separate PUBLIC repo.
1. Create a public repo (for example `sortwick-site`) and push only the contents of `website/` to its `main` branch (the files, `CNAME` included, at the repo root).
2. Repo Settings > Pages > Deploy from branch `main`, folder `/ (root)`. Custom domain `sortwick.com`, tick Enforce HTTPS once available.
3. In Hostinger hPanel > Domains > DNS / Nameservers, set:
   - A `@` 185.199.108.153
   - A `@` 185.199.109.153
   - A `@` 185.199.110.153
   - A `@` 185.199.111.153
   - CNAME `www` > `<user>.github.io`
   Remove any other A or AAAA record for `@` that points elsewhere. DNS can take up to a few hours.
