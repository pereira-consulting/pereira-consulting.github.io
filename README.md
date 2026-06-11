# Pereira Consulting website

Static site for www.pereiraconsulting.com, hosted on GitHub Pages.

## Structure

index.html (homepage), assets/ (logo, photography, favicon), briefs/ (Strategic Brief archive), CNAME, 404.html, robots.txt, sitemap.xml. The Lifecycle Advisory site remains in its own repo (Lifecycle) and is reachable at /Lifecycle/ once the custom domain is active on the account.

## Deploy (one-time)

1. Create a public repo named exactly: pereira-consulting.github.io (same account that owns the Lifecycle repo).
2. Upload the entire contents of this folder to the repo root (do not nest in a subfolder).
3. Repo Settings, Pages: source = Deploy from branch, branch = main, folder = /(root).
4. Settings, Pages, Custom domain: enter www.pereiraconsulting.com and save (the CNAME file already matches).
5. Tick Enforce HTTPS once the certificate is issued (minutes to an hour).

## DNS (at the domain registrar)

| Type  | Host | Value |
|-------|------|-------|
| CNAME | www  | pereira-consulting.github.io |
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |

Remove the Canva DNS records for www and @ when adding these. Propagation is usually under an hour; allow up to 24.

## After cutover

1. Verify https://www.pereiraconsulting.com loads with the padlock.
2. Verify /Lifecycle/ resolves on the custom domain.
3. Unpublish the Canva site.
4. Optional hardening: verify the domain under GitHub Settings, Pages, Verified domains to prevent takeover if Pages is ever disabled.

## Outstanding content items

- PE Assessment Tool: replace the "In build" card in index.html with the live URL when deployed.
- New Strategic Brief editions: drop the HTML into briefs/ and add a card in the insights section.

## Rollback

Re-publish the Canva site and restore the previous DNS records. Nothing in this repo needs to change.
