# Tatiana Shukletsova — accessibility portfolio

A small, fast, fully accessible static website. No build step, no framework, no
JavaScript required. You can open any `.html` file in a browser to preview it.

## Files

```
index.html                 Home
work.html                  Work (list of case studies)
case-iworkfornsw.html      Case study: I Work for NSW audit
about.html                 About
accessibility.html         Accessibility statement
contact.html               Contact
404.html                   "Page not found"
assets/style.css           All styling (one file)
downloads/                 The audit report (PDF + Excel)
```

## Preview it on your Mac

Double-click `index.html` — it opens in your browser. That's the whole site.
Everything works offline.

---

## Put it online with GitHub Pages (free)

1. Create a free account at **github.com**.
2. Click **New repository**. Name it `accessibility-portfolio` (or anything).
   Set it to **Public**. Create it.
3. On the repo page, click **Add file → Upload files**. Drag in *everything*
   from this folder (all the `.html` files, the `assets` folder, and the
   `downloads` folder). Commit.
4. Go to **Settings → Pages**. Under **Build and deployment → Source**, choose
   **Deploy from a branch**, pick branch **main** and folder **/ (root)**. Save.
5. Wait 1–2 minutes. Your site is live at
   `https://YOURUSERNAME.github.io/accessibility-portfolio/`.

To update it later, upload changed files the same way (step 3).

### Easier alternative — Netlify (no GitHub needed)

1. Go to **app.netlify.com**, sign up (free).
2. Choose **“Deploy manually / drag and drop”**.
3. Drag this whole folder onto the page. It's live in seconds at
   `https://SOMENAME.netlify.app` (you can rename it in Site settings).
4. To update: drag the folder again.

Both are free. Netlify is quicker to start; GitHub Pages keeps a history of
changes. You can move between them anytime — the files are identical.

### Custom domain (optional, ~A$15–25/yr)

Buy a domain (e.g. your name) from a registrar, then follow the “custom domain”
guide in GitHub Pages **Settings → Pages** or Netlify **Domain settings**.

---

## How to add the mobile-app case study later

1. Duplicate `case-iworkfornsw.html` and rename it `case-mobile-app.html`.
2. Replace the content with your mobile findings.
3. In `work.html`, find the “Coming soon · Mobile app” card and turn it into a
   real link: wrap it in `<a class="card-link" href="case-mobile-app.html"> … </a>`
   like the existing I Work for NSW card just above it.

## How to add articles / notes later

1. Create `articles.html` (copy the structure of `work.html` as a starting point)
   listing your articles, and one file per article (e.g. `article-focus-styles.html`,
   copy the structure of a content page like `about.html`).
2. Add a nav item in the `<nav>` of every page:
   `<li><a href="articles.html">Writing</a></li>`
   (add `aria-current="page"` to it only on the articles pages).

## How to add screenshots to a case study

Screenshots live in `assets/screenshots/`. One is already in place (the Sydney
Region VoiceOver capture). The **Evidence** section of `case-iworkfornsw.html`
already contains 8 more figures, fully written (alt text + captions) but hidden
inside a comment. To switch them on:

1. Save each screenshot into `assets/screenshots/` using these **exact** names:

   - `location-dropdown-open.png` — Location dropdown expanded (regions + chevrons)
   - `occupation-dropdown-expanded.png` — Occupation group expanded to sub-options
   - `location-announced-button-voiceover.png` — VoiceOver says "Locations, button"
   - `location-open-announced-button-voiceover.png` — dropdown open, still "button"
   - `hidden-screenreader-element-voiceover.png` — "for screen reader, edit text"
   - `more-options-less-options-voiceover.png` — More/Less options expanded
   - `css-disabled-no-checkboxes.png` — homepage with CSS turned off
   - `text-spacing-card-overlap.png` — cards overlapping at increased text spacing

2. In `case-iworkfornsw.html`, find `<!-- PENDING START` and delete that one line,
   then find `PENDING END -->` further down and delete that line too. All eight
   figures now appear.
3. Don't have one of the images? Just delete its single `<figure>…</figure>` block.

Each image opens full size in a new tab when selected, so viewers can inspect it.
The alt text is already written to describe both what the screenshot shows and the
problem it demonstrates.

## Keep it accessible when you edit

- One `<h1>` per page; use `<h2>`/`<h3>` in order, don't skip levels.
- Every image needs an `alt`. Decorative images: `alt=""`.
- Keep links as real `<a href>`; don't remove the focus styles in `style.css`.
- Check colour contrast if you change colours (aim for 4.5:1 on text).
