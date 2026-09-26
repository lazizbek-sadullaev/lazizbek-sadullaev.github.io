# Editing Guide — index.html

Your whole site is one file: `index.html`. It has three parts, in this order:

1. `<style>...</style>` — near the top. All colors, spacing, fonts. You rarely need to touch this.
2. `<header>`, `<nav>`, `<main>` — the actual content, split into `<section>` blocks (About, Research, Teaching, Skills, Awards, Contact).
3. `<footer>` — the bottom line.

You can find any part by searching (Ctrl+F / Cmd+F) for a word you see on the live page — e.g. search "Happiness Prediction" to jump straight to that project entry.

---

## Common edits

### Change any text
Find the sentence on the page, search for a few words of it in the file, and type over it. HTML tags (the stuff in `< >`) should stay — just edit the words between them.

### Edit or add a bullet-style entry (Research, Teaching, Awards)
Each item looks like this block. Copy one, paste it right above or below, and edit the text:

```html
<div class="entry">
  <div class="row">
    <span class="title">Your Title Here</span>
    <span class="meta">Optional date or location</span>
  </div>
  <div class="desc">
    Your description text here.
    <a href="https://your-link.com" target="_blank">Link text →</a>
  </div>
</div>
```

To delete an entry, delete the whole block from `<div class="entry">` to its matching `</div>`.

### Add a link (GitHub, LinkedIn, a project, etc.)
```html
<a href="https://the-url-goes-here.com" target="_blank">Text people click on</a>
```
`target="_blank"` makes it open in a new tab — leave it off for internal links like `./CV.pdf`.

### Change the profile photo
Replace `profile.jpg` in your repo with a new image **using the same file name**, or change the file name in this line and upload the new file with that name:
```html
<img src="profile.jpg" alt="Photo of Lazizbek Sadullaev">
```

### Add or remove a menu item (nav bar)
Two places must match — the nav link and the section it points to:
```html
<!-- in <nav>: -->
<a href="#newsection">New Section</a>

<!-- in <main>, add a whole new section: -->
<section id="newsection">
  <h2>New Section</h2>
  <p>Your content here.</p>
</section>
```
The `#newsection` and `id="newsection"` must match exactly, or the menu link won't jump anywhere.

### Change colors
Near the very top of the file, inside `:root { ... }`:
```css
--ink: #1B2A4A;    /* main text color */
--teal: #3E7C6B;   /* links and accents */
--gold: #C08A2E;   /* the small bar next to each heading */
--bg: #EDF1F5;     /* page background */
```
Change the hex codes to any color (e.g. from a picker like coolors.co or Google's "color picker" search tool).

---

## Checking your work
- **Fastest:** double-click `index.html` on your own computer — it opens in your browser exactly as it will look live, no upload needed.
- **On GitHub:** edit → commit → wait ~30 seconds → refresh `techdevbek.github.io`.

## If something breaks
The most common cause is a missing closing tag or a stray `<` or `>`. If the page looks broken after an edit, undo your last change (Ctrl+Z in the editor, or revert the commit on GitHub) and try again more narrowly — change one thing at a time.
