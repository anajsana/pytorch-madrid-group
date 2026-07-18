# PyTorch Madrid

Static site for the PyTorch Madrid community.

## Structure

```
pytorch-madrid/
├── index.html              ← page markup
├── styles.css              ← all CSS
├── assets/
│   └── pytorch-logo.svg    ← ADD YOUR LOGO HERE (.svg or .png)
├── .nojekyll               ← tells GitHub Pages to skip Jekyll
└── README.md
```

## Before you deploy

1. **Add your PyTorch logo** as `assets/pytorch-logo.svg` (or `.png` — the HTML has an automatic fallback from svg to png).
2. **Placeholders to update in `index.html`**:
   - `href="#"` on the **Join group** button (hero + nav) → your Luma group URL
   - `href="#"` on the **Coming soon on Luma** button (event card) → the specific event URL (also remove the `soon` class and change the label to something like `Register on Luma`)
   - `href="#"` on the **Submit your proposal** button → your talk-proposal form or `mailto:` (e.g. `mailto:hello@yourdomain.dev?subject=Talk proposal`)
   - Event date: inside the `.date-block`, change `<div class="day">TBD</div>` to the day number when confirmed
   - Event location: in `.event-meta`, replace `Madrid · October` with the actual venue

## Deploy to GitHub Pages

### 1. Create the repo

On [github.com/new](https://github.com/new):
- Repository name: `pytorch-madrid` (or whatever you want the URL slug to be)
- Public
- Don't add README/gitignore/license (this project already has one)

### 2. Push the code

From this folder, in the terminal:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/pytorch-madrid.git
git push -u origin main
```

Replace `<your-username>` with your GitHub handle (or org name).

### 3. Enable GitHub Pages

In the repo on GitHub:
1. Go to **Settings → Pages** (left sidebar).
2. Under **Build and deployment → Source**, pick **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. Save.
4. Wait ~30–60 seconds. GitHub will show a green banner with your URL:
   `https://<your-username>.github.io/pytorch-madrid/`

That's it — the site is live.

### 4. (Optional) Custom domain

If you own a domain (e.g. `pytorchmadrid.dev`):
1. In your DNS provider, add a `CNAME` record pointing your subdomain (or apex + ALIAS) to `<your-username>.github.io`.
2. In GitHub **Settings → Pages → Custom domain**, enter the domain. GitHub creates a `CNAME` file in your repo.
3. Wait for DNS to propagate (a few minutes to a few hours), tick **Enforce HTTPS** once available.

## Updating the site

Edit files locally, then:

```bash
git add .
git commit -m "Update event details"
git push
```

GitHub Pages redeploys automatically (~30s).

## Local preview

No build step, no dependencies:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Brand

- PyTorch orange: `#EE4C2C`
- Font: [Red Hat Display](https://fonts.google.com/specimen/Red+Hat+Display) (Google Fonts) — PyTorch's brand font.
- Follows the [PyTorch Brand Guidelines](https://pytorch.org/brand-guidelines/) — orange as accent, not fill.
