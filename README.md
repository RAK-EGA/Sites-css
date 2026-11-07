# Sites-css

Custom CSS for our websites, tracked in Git instead of the WordPress Customizer.

```
all-sites/main-en.css    shared by every English site (load first)
Courts/court-en.css      English site-only rules (load second)
DED/ded-en.css
Heritage/her-en.css
MUN/mun-en.css
RAKGOV/rak-en.css
PSD/psd-en.css           (empty for now)

*/…-ar.css               Arabic Customizer CSS, not split yet
```

## What goes where

- **`all-sites/main-en.css`**: every rule that is the same on all English sites,
  plus any rule that was on only some sites but had the same value wherever it appeared.
- **Site file**: design tokens and rules whose values differ between sites,
  page-ID rules, and rules a site turned off on purpose.

## Adding to a site

Put both links in the site's header, **shared first, then the site's own file**:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/all-sites/main-en.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/RAKGOV/rak-en.css">
```

Site files: `Courts/court-en.css`, `DED/ded-en.css`, `Heritage/her-en.css`,
`MUN/mun-en.css`, `RAKGOV/rak-en.css`. Paths are case-sensitive.

## After pushing a change

jsDelivr caches `@main` for up to ~12 hours. To refresh right away, open the same
URL with `purge.jsdelivr.net` in place of `cdn.jsdelivr.net`.

Once a site loads these files, empty its Customizer "Additional CSS" box —
it loads after these files and would override them.
