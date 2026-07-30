# Cambodia Vision Tour · October 2026

A single-page invitation site for the Living Water Foursquare **Cambodia Vision Tour**.
The whole site is one self-contained `index.html` — no build step, no dependencies.

## View it locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publish it (GitHub Pages)

This repo includes a workflow (`.github/workflows/deploy.yml`) that publishes the
site automatically whenever changes land on the **`main`** branch.

One-time setup:

1. In GitHub, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Merge this branch into `main`. The workflow runs and the site goes live at
   `https://jcobler77.github.io/cambodia_vision/`.

You can also trigger a deploy manually from the **Actions** tab
("Deploy to GitHub Pages" → **Run workflow**).

## Editing the content

Everything lives in `index.html`:

- **Hero, dates, price** — top of the `<body>`.
- **Itinerary** — the `#itinerary` section, one `<div class="day">` per day.
- **Route map** — inline SVG in the `#route` section.
- **Cost** — the `#cost` section.
- **Contact** — the `#contact` section (name, email, phone).

### Adding real photos

The gallery uses placeholder tiles. To use a real image, replace a tile like:

```html
<div class="photo"><span>Angkor Wat · Siem Reap</span></div>
```

with:

```html
<div class="photo" style="background-image:url('images/angkor.jpg');background-size:cover;">
  <span>Angkor Wat · Siem Reap</span>
</div>
```

Put image files in an `images/` folder in this repo.

### Social share preview

The `<head>` sets Open Graph / Twitter tags that point at
`og-image.png` (1200×630 recommended). Add that file to the repo root so links
shared by text or email show a preview card. If you use a custom domain, update
the `og:url`, `twitter:image`, and `canonical` URLs in `index.html` to match.

---

> **Note:** Dates and details are tentative and being finalized with in-country hosts.
> Not for wide distribution until dates confirm.
