# Editing cheat sheet

Most website content is ordinary Markdown inside `.qmd` files.

## Basic formatting

```markdown
# Main heading
## Section heading
### Subsection heading

**bold text**
*italic text*

[Link text](https://example.com)

- First item
- Second item
```

## Mathematics

Inline mathematics:

```markdown
The theory has $\mathcal{N}=1$ supersymmetry.
```

Displayed mathematics:

```markdown
$$
K = -\log\!\left(i\int_X \Omega\wedge\overline{\Omega}\right).
$$
```

## Add a publication

Copy one existing publication block in `publications.qmd` and replace its contents:

```markdown
::: {.publication}
<div class="pub-year">2027</div>
<div>
<h3>Title of the paper</h3>
<p>First Author, <strong>J. Monnee</strong>, and Other Author</p>
<p><em>Journal Name</em> <strong>volume</strong>, page or article number (2027)</p>
<p class="pub-links"><a href="DOI-URL">Journal</a> · <a href="ARXIV-URL">arXiv</a></p>
</div>
:::
```

## Add a talk

Copy one timeline block in `activities.qmd`:

```markdown
::: {.timeline-item}
<div class="timeline-date">Oct 2027</div>
<div class="timeline-content">
<h3>University or conference</h3>
<p>Title of the talk</p>
</div>
:::
```

## Add a navigation page

1. Create `newpage.qmd`.
2. Add this at the top:

```yaml
---
title: "New page"
description: "One-sentence description."
toc: true
---
```

3. Add the page to the `navbar.left` list in `_quarto.yml`:

```yaml
- text: "New page"
  href: newpage.qmd
```

## Keep the design consistent

Use the existing card and timeline blocks as templates. For ordinary content, prefer
Markdown headings and paragraphs rather than writing new HTML.
