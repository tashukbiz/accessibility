# Tatiana Shukletsova — accessibility portfolio

**Live site:** https://tashukbiz.github.io/accessibility

A small, fast, fully accessible static website. No build step, no framework, no
JavaScript. You can open any `.html` file in a browser to preview it, and
everything works offline.

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
assets/screenshots/        Evidence images for the case study
downloads/                 The audit report (PDF + Excel)
```

## Preview on your Mac

Double-click `index.html` — it opens in your browser. That's the whole site.

## Update the live site

The site is published with **GitHub Pages** from the `accessibility` repository
(branch `main`, folder `/root`). To change something:

1. Edit the file locally.
2. Go to the repo on github.com, open the folder that file lives in, then
   **Add file → Upload files**.
3. Drop the changed file in (uploading a file with the same name overwrites it),
   then **Commit changes**.
4. Wait about a minute for the site to rebuild.

Tip: when uploading several files, wait for the upload progress bar to finish
*before* clicking Commit — otherwise the commit can go through empty.

## Add the mobile-app case study later

1. Duplicate `case-iworkfornsw.html` and rename it `case-mobile-app.html`.
2. Replace the content with your mobile findings.
3. In `work.html`, find the "Coming soon · Mobile app" card and turn it into a
   real link: wrap it in `<a class="card-link" href="case-mobile-app.html"> … </a>`
   like the existing I Work for NSW card just above it.

## Add articles / notes later

1. Create `articles.html` (copy the structure of `work.html`) listing your
   articles, plus one file per article (copy a content page like `about.html`).
2. Add a nav item to the `<nav>` on every page:
   `<li><a href="articles.html">Writing</a></li>`
   (add `aria-current="page"` to it only on the articles pages).

## Add more evidence screenshots

Evidence images live in `assets/screenshots/` (named `H-01.jpg` … `H-21.png`)
and appear in the **Evidence** section of `case-iworkfornsw.html`. To add another:

1. Save the image into `assets/screenshots/`.
2. In `case-iworkfornsw.html`, copy one existing `<figure>…</figure>` block in the
   Evidence gallery and update the filename, the `alt` text, and the caption.

Write `alt` text that describes both what the screenshot shows **and** the problem
it demonstrates — that's part of doing accessibility well.

## Keep it accessible when you edit

- One `<h1>` per page; use `<h2>`/`<h3>` in order, don't skip levels.
- Every image needs an `alt`. Decorative images: `alt=""`.
- Keep links as real `<a href>`; don't remove the focus styles in `style.css`.
- If you change colours, keep text contrast at 4.5:1 or better.
