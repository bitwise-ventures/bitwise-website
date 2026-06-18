# bitwise-website

The landing page for **bitwise.ventures**, served free via GitHub Pages.

Single self-contained `index.html` (inline CSS, no build step, no dependencies).
Just edit the file and push — GitHub Pages redeploys automatically.

## Files

- `index.html` — the entire site.
- `CNAME` — tells GitHub Pages to serve at the custom apex domain `bitwise.ventures`.

## Deploy / how it works

GitHub Pages serves the `main` branch of this repo. The site is published at
the custom domain in `CNAME`.

### DNS (set at GoDaddy, where the domain is registered)

Apex domain (`bitwise.ventures`) → GitHub Pages requires four **A** records:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

(Optionally add the matching AAAA records for IPv6: `2606:50c0:8000::153`,
`...8001::153`, `...8002::153`, `...8003::153`.)

For the `www` subdomain, add:

```
CNAME   www   bitwise-ventures.github.io
```

Then in the repo: **Settings → Pages** → set the custom domain to
`bitwise.ventures` and enable **Enforce HTTPS** (after the cert provisions,
usually a few minutes to an hour).

## Local preview

```bash
python3 -m http.server -d . 8000   # then open http://localhost:8000
```
