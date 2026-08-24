# OVD Capital — website

Static site. No framework, no build dependencies beyond Python 3.

## Editing

Page content lives in `src/*.body.html`. Each file starts with a `title:` and
`desc:` line, a blank line, then the page's `<main>` content.

The shared masthead and footer live in `_head.part` and `_foot.part`, so the
navigation is defined once rather than in every page.

After editing, rebuild:

    python3 build.py

That regenerates the `*.html` files at the repo root. Commit those too — GitHub
Pages serves them directly.

## Local preview

    python3 -m http.server 4321

Then open http://localhost:4321

## Before launch

- Remove the `noindex` meta tag from `_head.part` and rebuild.
- Replace the reference placeholders on the homepage once Shawna and Jim have
  approved their own wording.
- Confirm `contact@ovdcapital.com` is live.
- Point `ovdcapital.com` at Pages and add a `CNAME` file. Email is tied to MX
  records and is unaffected by where the site is hosted.

## Structure

    src/            page bodies (edit these)
    _head.part      shared <head> and masthead
    _foot.part      shared closing band and footer
    css/site.css    all styles
    build.py        assembles src/ + partials into the root *.html
