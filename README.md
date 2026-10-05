# The Kolijar Chronicles: Info Hub

A GitHub Pages site for the series by Philip A. Hughes.

## Put it online

1. On GitHub, click **New repository**. Name it `<your-username>.github.io` for a root URL, or any name (e.g. `kolijar`) for `<your-username>.github.io/kolijar`. Keep it **Public**.
2. Upload everything in this folder (drag and drop works in the web UI), or push it with git.
3. If you used a name other than `<your-username>.github.io`, open `_config.yml` and set `url: "https://<your-username>.github.io"` and `baseurl: "/<repo-name>"`.
4. Go to **Settings → Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
5. Wait a minute or two, then visit your site.

## Editing

- Pages are Markdown files with a small header (`title`, `permalink`, `spoiler`).
- Edit the menu in `_config.yml` under `nav`.
- Colours and fonts live in `assets/css/style.css` (the `:root` block at the top).
- Add a character by copying `characters/serafina.md`, then adding it to `characters/index.md`.

## Spoiler rules of thumb

- Everything in a public repo is visible to anyone, including its edit history. Keep unreleased plot in a separate **private** repo.
- Set `spoiler:` on every page to the book a reader must have finished to read it safely.
- Book One pages here only use the official blurb. Extend them as you see fit.
