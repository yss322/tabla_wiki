# Tabla Beginner Lessons — wiki

A simple website of the beginner tabla curriculum (4 semesters), built with
[MkDocs Material](https://squidfunk.github.io/mkdocs-material/). Each lesson
lists its bols and has a slot for a demonstration video.

## Content lives in plain Markdown

- `docs/index.md` — home page (welcome + class instructions)
- `docs/semester-N/*.md` — one file per lesson
- `mkdocs.yml` — site config **and** the left-hand navigation (edit the `nav:`
  block when you add or rename a lesson)

The lessons were transcribed by hand from `SIPM Beginner Level Content.xlsx`
(kept in this repo for reference). There is no longer an auto-generator — edit
the Markdown directly.

## Preview locally

```bash
python3 -m mkdocs serve
```
Open http://127.0.0.1:8000/ . The page reloads automatically as you edit files.

## Add a video to a lesson

1. Upload the clip to YouTube and set its visibility to **Unlisted**.
2. Copy the 11-character video ID from the URL
   (`https://youtu.be/`**`dQw4w9WgXcQ`** or `watch?v=`**`dQw4w9WgXcQ`**).
3. In the lesson's `.md` file, find the section and its commented block:
   ```
   <!-- To add a video: uncomment the line below and paste the 11-char YouTube ID ...
   <iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" ...></iframe>
   -->
   ```
   Delete the `<!--` and `-->` lines and replace `VIDEO_ID` with your ID.
4. Save, check it in `mkdocs serve`, then publish (below).

## Add a new lesson

1. Create `docs/semester-N/NN-slug.md` with a `# Title` and `## Section`
   headings (copy the shape of an existing lesson, including the video
   placeholder blocks).
2. Add a line for it under the right semester in the `nav:` block of `mkdocs.yml`.

## Publish (free, on GitHub Pages)

One-time setup: create a GitHub repo and push this folder to it.

Every time you want to update the live site:
```bash
python3 -m mkdocs gh-deploy
```
This builds the site and pushes it to the `gh-pages` branch. GitHub serves it at
`https://<your-username>.github.io/<repo-name>/`.
