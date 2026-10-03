# Conor Marley — Portfolio

Static HTML/CSS site. No build step, no dependencies. Every page is a plain
`index.html` with its styles inline in a `<style>` block.

## Structure

```
index.html                         Home
about/index.html                   About
case-studies/pricing/index.html
case-studies/refer-a-friend/index.html
case-studies/freedom-mortgage/index.html
case-studies/accessibility/index.html
favicon.png, apple-touch-icon.png, logo.png
conor-marley-resume.pdf
paintings/                         Background art referenced by the home CSS
about/…, case-studies/*/…          Per-page images
```

## Important: must be served from the domain ROOT

Links and assets use root-relative paths (`/logo.png`, `/about/`,
`/case-studies/pricing/`, `/favicon.png`, `/conor-marley-resume.pdf`). The site
therefore has to be served at the root of a domain:

- **Works:** a GitHub user/org Pages site (`username.github.io`) or any repo
  with a custom domain (`conormarley.com`).
- **Breaks:** a GitHub *project* page served under a subpath
  (`username.github.io/repo-name/`) — the leading-`/` links would 404.

To deploy on GitHub Pages, push these files to the repo root (the `index.html`
must sit at the top level of what Pages serves) and point Pages at that
branch/root. Add a `CNAME` file if using a custom domain.

## Local preview

Serve from this folder's root, e.g.:

```
python3 -m http.server 8000
```

then open http://localhost:8000 . Opening the files directly via `file://`
will break the root-relative links.
