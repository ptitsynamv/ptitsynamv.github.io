# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-page personal CV site for Maria Ptitsyna, served by GitHub Pages at https://ptitsynamv.github.io/ straight from the `master` branch. It is plain static HTML/CSS built on the Start Bootstrap **Freelancer v6.0.3** theme (Bootstrap 4.5.0). There is no framework, no JavaScript of our own, and no build step.

The global Angular rules in the user's `~/.claude` config do not apply here.

## Commands

There are no build, lint, or test commands. `package.json` holds only metadata (no scripts, no dependencies). To preview, open `index.html` in a browser or serve the folder with any static server, e.g. `npx serve .`. Pushing to `master` deploys.

## Structure

- `index.html` is the entire site: a `masthead` header (name and title), an `#about` section (intro line plus a `list-group` of skill categories), and a `#contact` section whose icon links are large inline SVGs.
- `css/styles.css` is the compiled theme CSS (~10k lines, Bootstrap bundled in). There's no SCSS source in the repo, so any change goes straight into this file. The only local change so far is the commented-out `.list-group-item` border (around line 5049). Keep edits minimal and mark them clearly, because the file is otherwise vendor output.
- External assets load from CDNs in `<head>`: Font Awesome 5.13 (JS) and the Google Fonts Montserrat and Lato.
- `assets/img/favicon.ico` is also used as the `og:image`.

Earlier versions included the theme's portfolio images, contact form (`assets/mail/`) and `js/scripts.js`. They were deliberately removed, so don't bring them back.

## Editing content

Most updates are CV content edits in `index.html` (for example, adding a skill to the `<li class="list-group-item">` entries). Reuse the existing Bootstrap and theme classes (`page-section`, `divider-custom`, `list-group-item`, etc.) rather than adding new CSS.
