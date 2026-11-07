# site-styles

Custom CSS for our websites, tracked in Git instead of the WordPress Customizer.

```
all-sites/main.css     shared by every site (load first)
RAKGOV/style.css       site-specific overrides
Heritage/style.css
MUN/style.css
Courts/style.css
PSD/style.css
```

## Adding to a site

Put both links in the site's header, **shared first, then the site's own file**:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/GITHUB-USER/site-styles@main/all-sites/main.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/GITHUB-USER/site-styles@main/RAKGOV/style.css">
```

Swap `RAKGOV` for the site's folder. Folder names are case-sensitive in the URL.

## After pushing a change

jsDelivr caches `@main` for up to ~12 hours. To refresh right away, open the same
URL with `purge.jsdelivr.net` in place of `cdn.jsdelivr.net`.

Once a site loads these files, empty its Customizer "Additional CSS" box —
it loads after these files and would override them.
