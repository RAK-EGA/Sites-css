# Sites-css

Custom CSS for our websites, tracked in Git instead of the WordPress Customizer.

```
all-sites/main-en.css    shared by every English site
all-sites/main-ar.css    shared by every Arabic site (RTL)

<Site>/<site>-en.css     English site-only rules
<Site>/<site>-ar.css     Arabic site-only rules

Sites: Courts/court, DED/ded, Heritage/her, MUN/mun, RAKGOV/rak
PSD/psd-en.css is empty for now.
```

## What goes where

- **`all-sites/main-en.css`** / **`main-ar.css`**: every rule that is the same on all sites of that language,
  plus any rule that was on only some sites but had the same value wherever it appeared.
- **Site file**: design tokens and rules whose values differ between sites,
  page-ID rules, and rules a site turned off on purpose.

## Adding to a site

Each site loads two files in its header: **the shared file for its language first,
then its own file for the same language.**

English site (example: RAK):

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/all-sites/main-en.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/RAKGOV/rak-en.css">
```

Arabic site (example: RAK):

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/all-sites/main-ar.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Samy-Sorial/Sites-css@main/RAKGOV/rak-ar.css">
```

Swap `RAKGOV/rak` for `Courts/court`, `DED/ded`, `Heritage/her` or `MUN/mun`.
Paths are case-sensitive.

## After pushing a change

jsDelivr caches `@main` for up to ~12 hours. To refresh right away, open the same
URL with `purge.jsdelivr.net` in place of `cdn.jsdelivr.net`.

Once a site loads these files, empty its Customizer "Additional CSS" box —
it loads after these files and would override them.
