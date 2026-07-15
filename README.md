# AI for Meta-Science — NeurIPS 2026 Workshop Website

Static single-page website (plain HTML + CSS, no build step) for the NeurIPS 2026 workshop
**"AI for Meta-Science: Scaling and Organizing Science in the Age of AI Scientists"**.

Live at: https://ai4metascience.github.io/ (once deployed — see below)

## Files

- `index.html` — welcome page (about, dates, speakers, schedule, organizers, contact)
- `cfp.html` — full call for papers (scope, tracks, submission guidelines, dates, FAQ)
- `style.css` — all styling
- `.nojekyll` — tells GitHub Pages to serve files as-is (no Jekyll build)

Candidate speaker photos live OUTSIDE this repo in `../speaker_photos/<name>/`
(with `sources.md` per person). Once chosen, copy the photo into `assets/` here,
compress it, and swap the speaker's `<div class="avatar">XX</div>` for
`<img class="avatar" src="assets/name.jpg" alt="Name">`.

## Editing

Everything is in `index.html`. Common edits:

- **OpenReview link**: search for "OpenReview" — replace the "link soon" text and add the
  submission URL to the hero button area once the venue is set up.
- **Speakers**: duplicate a `<div class="person">` block in the `#speakers` section.
  To use real photos, replace `<div class="avatar">XX</div>` with
  `<img class="avatar" src="assets/name.jpg" alt="Name">` (put compressed photos < 200 KB in `assets/`).
- **Dates / schedule**: plain table rows in `#dates` and `#schedule`.
- **News**: add `<li>` items to the news box at the top.

Preview locally by opening `index.html` in a browser (no server needed).

## Deployment (GitHub Pages)

One-time setup:

1. Create a GitHub **organization** named `ai4metascience` (Settings → Organizations → New).
   An org (rather than a personal account) lets all co-organizers push.
2. In that org, create a **public** repository named exactly `ai4metascience.github.io`.
3. From this directory:
   ```bash
   git init
   git add .
   git commit -m "Initial workshop website"
   git branch -M main
   git remote add origin https://github.com/ai4metascience/ai4metascience.github.io.git
   git push -u origin main
   ```
4. GitHub Pages is enabled automatically for `<name>.github.io` repos
   (verify: repo → Settings → Pages → Source "Deploy from a branch", Branch `main`, `/ (root)`).
5. The site appears at https://ai4metascience.github.io/ within ~1–10 minutes.

Subsequent updates: edit, then `git add -A && git commit -m "..." && git push` —
changes go live in about a minute. Files can also be edited directly on github.com
(pencil icon), which commits and deploys in one step.
