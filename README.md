# CodeConnect 💻

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/HTML5%20%2B%20CSS3%20%2B%20JavaScript-Frontend-yellow?style=for-the-badge)

A developer project upload interface built with HTML, CSS, and JavaScript — with image preview via FileReader API, async tag validation, and simulated project publishing using Promises and async/await.

---

## Live Application

[CodeConnect Demonstration](https://codeconnect-two.vercel.app)

---

## Overview

CodeConnect is a project publishing interface for developers. Users can upload an image (previewed instantly in the browser without a server), fill in the project name and description, add tags from a predefined list, and publish. Every async operation — image reading, tag validation, and publishing — uses Promises and async/await, making the code easy to follow and extend.

---

## Architecture

```
codeconnect/
├── index.html          # Page structure — aside nav + main form
├── styles.css          # All styles — CSS custom properties, dark theme, Flexbox layout
├── scripts.js          # All interactivity — FileReader, Promises, async/await, event delegation
└── img/                # SVG icons and placeholder image
```

### Key JavaScript Concepts Applied

| Concept | How it shows up |
|---|---|
| **FileReader API** | `lerConteudoDoArquivo()` wraps `FileReader` in a Promise — reads the image and returns a base64 URL for preview |
| **Promises** | `lerConteudoDoArquivo()`, `verificaTagsDisponiveis()`, and `publicarProjeto()` all return Promises |
| **async/await** | All event handlers that call async functions use `await` inside `try/catch` blocks |
| **Event delegation** | Tag removal uses a single listener on the parent `ul` — checks `classList.contains("remove-tag")` instead of attaching to each tag |
| **DOM manipulation** | Tags are created with `document.createElement("li")` and appended dynamically |
| **setTimeout simulation** | Tag validation and publishing simulate async API calls with `setTimeout` |
| **Form reset** | Discard button resets the form, restores the placeholder image, and clears all tags |
| **CSS Custom Properties** | Dark theme managed via `:root` — `--background-color`, `--primary-color`, `--tag-color` |
| **Google Fonts** | Prompt font family with multiple weights |

---

## Features

- **Image Upload** — click to select an image; preview appears instantly using FileReader API
- **Tag System** — type a tag and press Enter; validated against a predefined list with a 1s simulated delay
- **Remove Tags** — click the X on any tag to remove it via event delegation
- **Publish** — simulates an API call with random success/failure after 2 seconds
- **Discard** — resets the entire form, image, and tag list in one click

---

## How to Run

```bash
git clone https://github.com/victorhubarb/codeconnect.git
cd codeconnect
```

Open `index.html` in your browser. No build step needed.

---

## Technologies

- **HTML5 / CSS3 / JavaScript**
- **FileReader API** — client-side image reading and preview
- **Promises + async/await** — asynchronous flow control
- **Google Fonts** — Prompt

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
