# salkooheji.github.io

Source for my personal site, live at [salkooheji.github.io](https://salkooheji.github.io).

A single page covering what I work on, the projects I have built with their
measured results, my experience, and how to reach me.

## Structure

```
index.html      the entire site: markup, styles and one small script
portrait.png    header portrait
```

No build step, no dependencies, no framework. The only external request is the
Google Fonts stylesheet. Open `index.html` in a browser to preview it exactly
as it will appear live.

## Editing

Everything lives in `index.html`.

- Content sits in the `<body>`, in plain HTML sections: projects, experience,
  leadership, education, skills.
- Styles sit in the single `<style>` block in the `<head>`.
- Colours, fonts and spacing are CSS custom properties defined in `:root`.
  Change a token there and it updates everywhere.

To add a project, copy an existing `.proj` block and edit the metric, title,
description and stack. The metric is the first thing a reader sees, so it
should be the number that best represents the project.

## Design tokens

| Token | Value | Used for |
| --- | --- | --- |
| `--navy` | `#0F1B2E` | headings, names, emphasis |
| `--brass` | `#9C7A3C` | metrics, rules, accents, links on hover |
| `--char` | `#262626` | body text |
| `--slate` | `#6B7280` | captions and secondary text |
| `--hair` | `#D8D2C4` | dividers and borders |
| `--paper` | `#FCFBF9` | background |
| `--measure` | `64ch` | maximum line length for all prose |

Type is Lora for display, IBM Plex Sans for body, and IBM Plex Mono for figures
and labels. The same palette and two-tone name treatment are used on my CV, so
changes here should stay in step with that.

## Layout notes

Sizing is fluid rather than fixed. Spacing, type and the portrait scale with
`clamp()`, and project rows collapse to a single column below 820px. Prose
blocks share one `--measure` so every paragraph wraps at the same width.

The page respects `prefers-reduced-motion`, and the scroll reveal falls back to
plain visible content where `IntersectionObserver` is unavailable.

## Deployment

GitHub Pages serves the `main` branch from the repository root. Pushing to
`main` publishes the site within a minute or two.