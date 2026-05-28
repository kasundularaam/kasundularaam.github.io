# kasundulara.me — a notebook, not a portfolio

A hand-built, framework-free "place" served by GitHub Pages. The metaphor is a
**lab notebook / terminal**: directories are the navigation, pages are linked
freely rather than organized rigidly, and new pages can be dropped in anytime.

## How it's wired

```
/                  boot screen / home terminal
/theme.css         the ONE shared stylesheet (terminal dark + monospace)
/_template.html    copy this to make a new page
/404.html          themed not-found page
/whoami.html       who I am + skills
/now.html          /now page — what I'm doing right now
/projects/         index.html → one .html per project
/papers/           index.html → one .html per paper note
/thoughts/         index.html — short notes (inline .entry blocks)
/hobbies/          index.html — life away from the keyboard
/assets/           images
```

## Adding a new page (the whole workflow)

1. **Copy** `_template.html` to its new home, e.g. `projects/new-thing.html`.
2. **Edit** the `<title>`, `<meta description>`, and `<link canonical>`.
3. **Fix** the breadcrumb (`.crumb`) so the path matches where the file lives.
4. **Write** your content. Use plain language — it's a notebook.
5. **Link it**: add one `<li>` to the relevant index (`projects/index.html`,
   `papers/index.html`, etc.). Optionally cross-link from any other page.
6. **Commit & push** — GitHub Pages publishes it live.

That's it. No build step, no dependencies, no install.

## The design rules (so it stays coherent)

- **One shared theme.** Every page links `/theme.css`. Don't fork the base look;
  put page-specific CSS in that page's own `<style>` block.
- **Root-absolute paths.** Always link with a leading slash (`/papers/`,
  `/theme.css`) so links work from any folder depth.
- **Trailing slash = directory, no slash = file.** A terminal habit that doubles
  as a visual cue in the directory listings.
- **Link liberally.** A page that links nowhere isn't part of the place. Wire new
  pages into at least one index and, ideally, a couple of sibling pages.
- **Seedlings are fine.** Mark unfinished pages with 🌱; ship them anyway.

## Reusable bits in theme.css

`.wrap` (page container) · `.topbar` + `.crumb` (breadcrumb) · `.prompt` (command
line) · `.dir` (directory listing / link list) · `.entry` (dated notebook entry) ·
`.tags`/`.tag` (chips) · `.note` (highlight box) · `.bul` (bulleted list) ·
`.cursor` (blinking cursor) · `code`/`pre` (code blocks).

## Local preview

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```
