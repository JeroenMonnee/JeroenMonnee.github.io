# Homepage text rendering fix v5.1

This patch fixes two rendering problems:

1. The large white copy of “Jeroen Monnee” above the artwork.
2. Multiple overlapping layers in the hero affiliation and research description.

The cause was Quarto/Pandoc interpreting Markdown headings and deeply nested fenced
divs in an unexpected way. The homepage body is now written as one explicit raw-HTML
block, giving the browser a single, unambiguous DOM structure.

Additional defensive CSS ensures that the hero text cannot inherit duplicated layers,
text shadows, transforms, or abnormal line wrapping.

No image files were changed.
