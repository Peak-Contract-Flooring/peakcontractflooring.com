# Peak Contract Flooring — Hugo Site Scaffold

A ready-to-overlay content package for the **Hugo Hero theme** (Zerostatic),
structured like the best flooring contractor sites (Pacific Hardwood's named-project
gallery + Signature Custom Flooring's estimate-driven homepage).

## What's in here

```
peak-flooring-site/
├── README.md              <- you are here
├── config-notes.md        <- settings to change in the theme's config.toml
├── photo-shot-list.md     <- exactly which photos to collect before launch
├── content/
│   ├── homepage/          <- homepage sections (hero, work preview)
│   ├── services/          <- one page per service
│   ├── work/              <- THE GALLERY: one page per named project
│   ├── about/             <- company story
│   └── contact/           <- contact / free estimate page
└── data/                  <- (empty; theme uses this for features data)
```

## Setup (one time, ~10 minutes)

Requires [Hugo](https://gohugo.io/installation/) and git.

```bash
# 1. Create the site
hugo new site peakflooring && cd peakflooring

# 2. Clone the Hero theme
git clone https://github.com/zerostaticthemes/hugo-hero-theme.git themes/hugo-hero-theme

# 3. Copy the theme's example content (gives you a working config + all sections)
cp -a themes/hugo-hero-theme/exampleSite/. .

# 4. Overlay this package's content on top (from wherever you unzipped it)
cp -a /path/to/peak-flooring-site/content/. content/

# 5. Edit config.toml using config-notes.md in this package

# 6. Run it
hugo server
# -> open http://localhost:1313
```

## Important: front-matter check

These content files follow Zerostatic's conventions (title / date / weight / image).
After step 3, compare any file that renders oddly against its counterpart in
`themes/hugo-hero-theme/exampleSite/content/` — if the theme expects a field name
this package doesn't use (e.g. a specific hero image param), copy that field over.
Everything else (the copy, structure, and organization) stays as written.

## Adding a new job later (the whole point)

```bash
hugo new work/smith-kitchen-newnan.md
```

Then edit the file: set the title, drop 5–10 photos in `static/images/work/smith-kitchen/`,
reference them in the page body, commit, push. Done. Use the existing project files
in `content/work/` as templates — they show the pattern.

## Contact form

Hugo is static, so the form needs a backend. Two easy options:

- **Netlify Forms** (if hosting on Netlify): add `netlify` attribute to the form tag. Free tier: 100 submissions/mo.
- **Formspree**: point the form action at your Formspree endpoint. Free tier: 50/mo.

The contact page content includes a note where this goes. Until it's wired up,
the phone number and email links work fine on their own.

## Replace before launch

Search the content folder for `[BRACKETS]` — every placeholder that needs his
real info (years in business, service area, phone, certifications) is marked that way.

```bash
grep -rn "\[" content/ | grep -v "](/"
```

## Theme
Vendored copy of [hugo-hero-theme](https://github.com/zerostaticthemes/hugo-hero-theme) at commit 6c3c2da (nested .git removed). Site-level overrides live in layouts/ and assets/ — don't edit the theme directly.
