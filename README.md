# Jeroen Monnee — Academic Website

A compact academic website built with [Quarto](https://quarto.org/) and published
automatically through GitHub Pages.

For installation instructions, read [`START-HERE.md`](START-HERE.md).

For editing examples, read [`EDITING-CHEATSHEET.md`](EDITING-CHEATSHEET.md).

## Local preview

```bash
quarto preview
```

## Render the website

```bash
quarto render
```

The rendered website is written to `_site/`. GitHub Actions handles rendering and
deployment automatically whenever changes are pushed to `master` or `main`.
