# tacitcreatives.com

Static site for TACIT. Single self-contained file — all CSS and the wordmark
SVG are inlined, so there is nothing to build and nothing to break.

## Deploy (GitHub Pages)

1. Create a public repo, e.g. `tacitcreatives`.
2. Upload `index.html` and `CNAME` to the repo root.
3. Settings → Pages → Source: `main` branch, `/ (root)` → Save.
4. Settings → Pages → Custom domain: enter `tacitcreatives.com` → Save.
5. Point DNS at GoDaddy (see below).
6. Once DNS resolves, tick **Enforce HTTPS** (certificate can take up to 24h).

## DNS at GoDaddy

Replace the existing `A @ Parked` record with four A records:

    A   @   185.199.108.153
    A   @   185.199.109.153
    A   @   185.199.110.153
    A   @   185.199.111.153

Change the existing `www` CNAME from `tacitcreatives.com` to:

    CNAME   www   <your-github-username>.github.io

Leave every mail record exactly as it is — MX, SPF (TXT @ v=spf1…),
DKIM (3 CNAMEs), DMARC (TXT _dmarc), and the protonmail-verification TXT.
None of them are affected by the website records.
