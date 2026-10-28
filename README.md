# CodeConnect

A project-publishing form for developers, in plain HTML, CSS and JavaScript. You pick a cover image, add tags, and "publish". The image preview works in the browser, and the tag check and the publish step are simulated with Promises, so the page has no backend.

**Live demo:** [codeconnect-two.vercel.app](https://codeconnect-two.vercel.app)

## What it does

- **Image preview.** Choosing a file shows it immediately. `lerConteudoDoArquivo()` wraps `FileReader` in a Promise and resolves with the image as a data URL plus its file name.
- **Tags.** Type a tag and press Enter. After a one-second fake delay (`setTimeout` inside a Promise), the tag is accepted only if it is on the allowed list: Front-end, Programação, Data Science, Full-stack, HTML, CSS or JavaScript. An unknown tag gets an alert. Clicking the X on a tag removes it, using one click listener on the parent `<ul>` instead of one per tag (event delegation).
- **Publish.** Waits two seconds, then succeeds or fails at random (`Math.random() > 0.5`). The handler uses `async/await` with `try/catch` for both outcomes.
- **Discard.** Resets the form, puts the placeholder image back and clears the tags.

The interface is in Portuguese. The styles use CSS custom properties for the dark theme and the Prompt font from Google Fonts.

## Run it

No build step. Clone the repo and open `index.html` in a browser.

```bash
git clone https://github.com/victorhubarb/codeconnect.git
cd codeconnect
```

## Project structure

```
index.html    Sidebar and the form
styles.css    Dark theme, Flexbox layout
scripts.js    All behavior
img/          SVG icons and the placeholder image
```

## Known gaps

- Publishing is a simulation. The name, description and tags are collected but never sent anywhere.
- The form has no validation, so you can publish an empty project.
- Tag matching is case-sensitive, so "html" is rejected while "HTML" is accepted.
- There are no media queries, so the layout is made for desktop screens.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
