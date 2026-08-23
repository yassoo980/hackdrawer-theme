# Hack Drawer — Shopify Theme

Custom Liquid theme for an "everyday hacks" store (makeup / kitchen / home).
Built as an Online Store 2.0 theme (JSON templates + Liquid sections), so everything
on the homepage is editable in Shopify's theme editor after install.

## What's included
- `layout/theme.liquid` — page shell, loads fonts + theme.css
- `sections/` — header, footer, hero, category-grid, featured-collection, trust-strip,
  newsletter, plus main-product / main-collection / main-cart / main-search /
  main-page / main-article / main-blog / main-404
- `templates/` — JSON templates wiring sections to each page type
- `assets/theme.css` — all styling from the design mockup
- `snippets/product-card.liquid` — reusable product card (pulls real product data)

## 1. Push this folder to GitHub

```bash
cd hackdrawer-theme
git init
git add .
git commit -m "Initial Hack Drawer theme"
git branch -M main
git remote add origin https://github.com/yassoo980/hackdrawer-theme.git
git push -u origin main
```

(Create the empty repo `hackdrawer-theme` on github.com/yassoo980 first — no README/license,
so it stays empty for this push.)

## 2. Connect the repo to your Shopify store

1. In Shopify admin: **Online Store → Themes → Add theme → Connect from GitHub**
2. Authorize the Shopify GitHub app if you haven't already
3. Select the `hackdrawer-theme` repo and the `main` branch
4. Shopify pulls it in as a new (unpublished) theme

## 3. Preview and customize

Open the new theme's **Customize** view. On the homepage you can:
- Edit the hero headline/subhead and the 4 floating hack cards
- Point the 3 category cards at real collections (create "Makeup", "Kitchen", "Home"
  collections first)
- Point "Featured collection" at whichever collection you want to spotlight, and set
  how many products to show

**Tip:** add a product metafield `custom.fix_line` (single line text) to any product —
if set, it shows as the "Problem: ... Fix: ..." callout on the product card. Optional;
falls back gracefully if you skip it.

## 4. Local development (optional but recommended)

```bash
npm install -g @shopify/cli @shopify/theme
shopify theme dev --store=your-store.myshopify.com
```

This gives you a live local preview at `localhost:9292` that hot-reloads as you edit
files. Push commits to `main` (or open a PR) and Shopify re-syncs the connected theme
automatically.

## 5. Go live

Once it looks right: **Themes → Actions → Publish**.

## Not included yet (add if you need them)
- Password page / customer account pages (Shopify's defaults are used for now)
- AJAX cart drawer (cart currently does a normal page reload to `/cart`)
- Real product photography — placeholders are emoji icons until you upload images
