# ptitsynamv.github.io

[![Live site](https://img.shields.io/badge/live-ptitsynamv.github.io-2c3e50?logo=githubpages&logoColor=white)](https://ptitsynamv.github.io/)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Bootstrap 4.5](https://img.shields.io/badge/Bootstrap-4.5-7952B3?logo=bootstrap&logoColor=white)
![Font Awesome 5](https://img.shields.io/badge/Font_Awesome-5.13-528DD7?logo=fontawesome&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/hosted_on-GitHub_Pages-222222?logo=github&logoColor=white)
![License: MIT](https://img.shields.io/badge/license-MIT-green)

The personal CV site of **Maria Ptitsyna**, a full-stack developer. It's live at **https://ptitsynamv.github.io/**.

## Overview

The site gives recruiters and collaborators one stable URL with an up-to-date skills summary and a way to get in touch, without the overhead of maintaining a web app.

It's a single static page:

| Section | Contents |
| --- | --- |
| **Header** | Name, role, core stack and in-page navigation |
| **About** | Summary and headline numbers (years of experience, certifications) |
| **Experience** | Roles at Grid Dynamics, EPAM, MaybeWorks and earlier PHP positions, with highlights and stack |
| **Skills** | Grouped skill tags plus spoken languages |
| **Side Projects** | Four selected public GitHub repos |
| **Certifications & Education** | AWS and Anthropic certifications with Credly links, and degrees |
| **Contact** | Links to [LinkedIn](https://www.linkedin.com/in/ptitsynamv/), [GitHub](https://github.com/ptitsynamv) and email |

The content is taken from a private career-data repository (`career-ops`), which is the source of truth for every fact on the page.

## Architecture

```
.
├── index.html            # The entire site: markup, content and inline SVG icons
├── css/styles.css        # Compiled Start Bootstrap Freelancer theme (includes Bootstrap 4.5)
├── assets/img/favicon.ico
└── package.json          # Repository metadata only, with no scripts or dependencies
```

The site is deliberately simple:

- **Static, with no build step.** The files in the repo are exactly what GitHub Pages serves. Nothing needs compiling, bundling or installing, so a push to `master` is a deploy.
- **Theme-based layout.** The page uses the [Start Bootstrap Freelancer](https://startbootstrap.com/theme/freelancer) theme (v6.0.3), cut down to the header, About and Contact sections. The theme's portfolio, contact form and JavaScript were removed because a CV site doesn't need them.
- **No custom JavaScript.** All layout and responsiveness come from Bootstrap's CSS grid and utility classes.
- **Inline SVG contact icons.** The icons are embedded in the page rather than loaded as image files.
- **Open Graph metadata.** The `og:` tags make shared links show a title and description.

External resources load from CDNs: Font Awesome 5.13 (JS) and Google Fonts (Montserrat and Lato).

## Quick start

### Prerequisites

- Any modern web browser
- *Optional:* [Node.js](https://nodejs.org/), for running a local static server

### Install

```bash
git clone https://github.com/ptitsynamv/ptitsynamv.github.io.git
cd ptitsynamv.github.io
```

There are no dependencies to install.

### Run

Open `index.html` directly in a browser, or serve the folder locally:

```bash
npx serve .
# or
python -m http.server 8000
```

### Test

The project has no automated tests. To check a change, preview the page locally at both desktop and mobile widths before pushing.

### Deploy

Push to `master`. GitHub Pages publishes the repository root automatically.

## Editing content

Each part of the page is a `<section>` in `index.html` with a matching `id` (`#about`, `#experience`, `#skills`, `#projects`, `#credentials`, `#contact`). Update the facts in `career-ops` first, then copy them here.

- **Roles:** one `<article class="card job">` per role in `#experience`.
- **Skills:** `<span class="tag">` items inside the `skill-group` blocks in `#skills`.
- **Styles:** `css/styles.css` is compiled theme output and there's no SCSS source. Site-specific styles (masthead nav, stats, job cards, skill tags) live in the commented block at the end of the file. Add new rules there.

## Credits and license

- Theme: [Start Bootstrap Freelancer](https://github.com/StartBootstrap/startbootstrap-freelancer) © Start Bootstrap, MIT
- Framework: [Bootstrap](https://getbootstrap.com/) © The Bootstrap Authors, MIT

This project is licensed under the MIT License, as declared in `package.json`.
