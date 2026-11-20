# slimaneasv.github.io

Personal website, served by GitHub Pages at https://slimaneasv.github.io.

GitHub builds it with Jekyll on every push; there is nothing to compile yourself.

## Layout

```
index.html             Home page
random.html            Random page (content comes from _data/random.yml)
art-and-essays.html    Art & Essays page (essays from _essays/, art from _data/art.yml)
_essays/               One Markdown file per essay
_data/random.yml       Entries for the Random page
_data/art.yml          Entries for the Art section
_layouts/              Page shell (header, nav, footer) and the essay layout
assets/style.css       All the styling
pictures/              Images (profile photo, logos in pictures/logos/, art, essay images)
files/                 PDFs and other downloads (CV, slides, ...)
_config.yml            Site title, CV path, settings
```

## Common edits

**Profile photo.** Save a square-ish photo as `pictures/profile.jpg`. It appears on the home page automatically; with no file, nothing shows.

**Logos.** Save them as `pictures/logos/uoft.png`, `inria.png` and `pleias.png` (transparent PNGs look best). They show up in a row under the intro; any that are missing are hidden.

**Colours.** Everything red comes from `--red` at the top of `assets/style.css`.

**CV.** Replace `files/Resume_Slimane_ASV.pdf`. If you rename it, update `cv:` in `_config.yml`.

**Something on the Random page.** Add an entry at the top of `_data/random.yml`:

```yaml
- date: Dec 2026
  title: Something I made
  where: Somewhere
  url: https://example.com        # or a file in the repo: /files/slides.pdf
  note: A sentence about it. [Markdown links](https://example.com) work.
```

**An essay.** Copy `_essays/example.md` to e.g. `_essays/on-chaos.md` (the URL becomes `/essays/on-chaos/`), edit the title, date and description, delete the `published: false` line, and write in Markdown. Add `math: true` to use LaTeX: `$$x^2$$` inline, or `$$ ... $$` on its own lines for display math. Essays with a date in the future don't appear until that date.

**A piece of art.** Put the image in `pictures/` and add an entry to `_data/art.yml`:

```yaml
- image: my-painting.jpg
  title: Untitled
  year: 2026
  medium: Oil on canvas
```

**Home page text.** Edit `index.html` directly; it's plain HTML.

## Preview locally (optional)

With Ruby installed:

```
bundle install
bundle exec jekyll serve
```

then open http://localhost:4000.
