# zola-static-site

A basic static site starter built with **Zola** — the fast static site
generator written in **Rust**.

## Prerequisites

- [Zola](https://www.getzola.org/) (v0.18+). If you don't have it installed,
  see the installation options in the Zola docs.

> Note: the `zola` binary is **not** installed on this machine; running the
> build/serve commands requires installing it first.

## Project structure

    .
    ├── config.toml          # Site-wide configuration
    ├── content/             # Markdown content
    │   ├── _index.md        #   Home page
    │   ├── about/index.md   #   /about/ page
    │   └── reports/         #   Reports section (/reports/)
    │       ├── _index.md            #   /reports/ index (all reports by topic)
    │       └── linux/               #   Topic: /reports/linux/
    │           ├── _index.md        #     Topic page
    │           └── linux-trends-2026/index.md  #   Report page
    ├── templates/           # Tera templates
    │   ├── base.html        #   Base layout
    │   ├── index.html       #   Home (section) template
    │   ├── page.html        #   Generic page template
    │   ├── reports.html     #   /reports/ index (groups reports by topic)
    │   ├── topic.html       #   Topic section page
    │   └── report.html      #   Individual report page
    ├── static/style.css     # Static asset, copied verbatim to output
    ├── sass/                # Optional Sass/SCSS (compiled to CSS)
    └── .gitignore

## Commands

Build the static site into `public/`:

    zola build

Start a local dev server with live reload:

    zola serve

Print a summary of the site (pages, sections, taxonomies):

    zola check

## Adding a new report

To publish a report at `/reports/<topic>/<slug>/`:

1. Create the topic section if it doesn't exist yet:
   `content/reports/<topic>/_index.md` with front matter
   `template = "topic.html"`.
2. Drop the report in as a page:
   `content/reports/<topic>/<slug>/index.md` with front matter that includes
   `title`, `date`, `template = "report.html"`, and
   `[extra] topic = "<topic>"`.
3. Rebuild with `zola build` (or it auto-rebuilds under `zola serve`).

The `/reports/` index and the topic page both list reports automatically;
no template edits are needed for each new report.