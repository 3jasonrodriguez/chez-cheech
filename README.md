# Recipe Box

A Jekyll site (Minimal Mistakes theme) for browsing recipes by category, ingredient tag, and rating, with client-side search.

## Structure

- `_recipes/` — one markdown file per recipe. Front matter: `title`, `categories`, `tags`, `rating`, `description`, `image` (optional). Content body holds `## Ingredients`, `## Steps`, `## Changelog`.
- `_layouts/recipe.html` — single recipe page layout.
- `_includes/recipe-card.html` — card used on the landing page and browse pages.
- `index.html` — landing page: search bar + card grid of all recipes.
- `categories.html` / `tags.html` — auto-generated browse pages, one section per category/tag.
- `assets/css/custom.css` — visual styling on top of the theme.

## Publish to GitHub Pages

1. Create a new GitHub repo (e.g. `recipes`).
2. Push this folder as the repo root:
   ```
   git init
   git add .
   git commit -m "Initial recipe site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repo's **Settings → Pages**, set Source to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. If this is a **project site** (not `<username>.github.io`), set `baseurl: "/<repo-name>"` in `_config.yml`. If it's a user site, leave `baseurl` blank and set `url` to `https://<username>.github.io`.
5. Wait a minute or two for the first build, then visit the Pages URL shown in Settings.

## Preview locally (optional)

Requires Ruby + Bundler.

```
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## Adding a new recipe

Drop a new `.md` file in `_recipes/` following the schema in `hashbrown-skillet-with-over-easy-eggs.md`, then commit and push (or edit directly in GitHub's web UI). No build step to run yourself — GitHub Pages rebuilds automatically on push.
