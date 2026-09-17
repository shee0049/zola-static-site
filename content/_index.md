+++
title = "Home"
description = "Welcome to the home page of this Zola site."

# When `+++` is used without a `template` override, Zola renders this
# section with templates/index.html (the site's home template).
+++

# Welcome to My Zola Site

This is a **basic static site** built with [Zola](https://www.getzola.org/),
the fast static site generator written in **Rust**.

Here's a quick list of what's included in this starter:

- Markdown-based content with front matter
- Base + page HTML templating (Tera templates)
- A Sass stylesheet
- Pretty URLs out of the box

Visit the [About page](/about/) to see a sub-page, or read this section's
content — everything you write under `content/` gets rendered to static HTML
by `zola build`.

> Tip: run `zola serve` to preview locally, then `zola build` to produce the
> static site in the `public/` directory.