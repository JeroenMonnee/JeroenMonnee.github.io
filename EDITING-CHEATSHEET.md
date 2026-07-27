# Editing cheat sheet

Most website content is ordinary Markdown inside `.qmd` files.

## Where to edit

| Change | File |
|---|---|
| Homepage and contact text | `index.qmd` |
| Research themes | `research.qmd` |
| Publications and summaries | `publications.qmd` |
| Talks, service, and outreach | `activities.qmd` |
| Teaching and supervision | `teaching.qmd` |
| Navigation and footer | `_quarto.yml` |
| Visual styling | `styles.css` and `theme.scss` |
| CV PDF | `files/Jeroen_Monnee_CV.pdf` |

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

Use dollar signs, which Quarto processes reliably:

```markdown
The theory has $\mathcal{N}=1$ supersymmetry.
```

For displayed mathematics:

```markdown
$$
K = -\log\!\left(i\int_X \Omega\wedge\overline{\Omega}\right).
$$
```

## Add a publication

Copy one existing publication block in `publications.qmd` and replace its contents:

```markdown
:::: {.publication}
::: {.pub-year}
2027
:::
::: {.publication-body}
### Title of the paper

First Author, **J. Monnee**, and Other Author

*Journal Name* **volume**, article number (2027)

::: {.pub-summary}
One or two sentences explaining the paper's main contribution.
:::

::: {.pub-links}
[DOI](https://doi.org/...) ·
[arXiv](https://arxiv.org/abs/...)
:::
:::
::::
```

## Add a talk

Copy one timeline item in `activities.qmd`:

```markdown
::: {.timeline-item}
::: {.timeline-date}
Oct 2027
:::
::: {.timeline-content}
### University or conference

*Title of the talk*
:::
:::
```

## Update the CV

Replace `files/Jeroen_Monnee_CV.pdf` with the new PDF while keeping exactly the same
filename. No page source needs to be edited.

## Preview locally

From the repository folder:

```bash
quarto preview
```

After checking the result, commit and push through GitHub Desktop.
