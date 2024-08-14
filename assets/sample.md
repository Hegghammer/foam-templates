---
author: Thomas Hegghammer
---

# Export to PDF

This #recipe shows how to export a note to PDF.

## Required extensions

- **[vscode-pandoc](https://marketplace.visualstudio.com/items?itemName=chrischinchilla.vscode-pandoc)**

## Required third-party tools

- [Pandoc](https://pandoc.org/installing.html)
- A [LaTeX distribution](https://www.latex-project.org/get/) such as TeXLive (Linux), MacTeX (MacOS), or MikTeX (Windows)

Check that Pandoc is installed by opening a terminal and running `pandoc --version`.

Check that Pandoc can produce PDFs with LaTeX by running the following in the terminal.

```
echo It is working > test.md
pandoc test.md -o test.pdf
```

## Instructions

1. Create a folder in your workspace named `.pandoc`. Take note of the full path to this directory. The rest of this recipe will refer to this path as `$WORKSPACE/.pandoc`.

2. Download the template file [`foam.latex`](https://raw.githubusercontent.com/Hegghammer/foam-templates/main/foam.latex) from [Hegghammer/foam-templates](https://github.com/Hegghammer/foam-templates) and place it in `$WORKSPACE/.pandoc`.

3. In VSCode, open `settings.json` for your user (or just for your workspace if you prefer), and add the following line:

```
"pandoc.pdfOptString": "--from=markdown+wikilinks_title_after_pipe --resource-path $WORKSPACE/.pandoc --template foam --listings",
```

Make sure to replace `$WORKSPACE/.pandoc` with the real full path to the `.pandoc` directory you created earlier.

4. Open a Foam note in VSCode.

5. Press `Ctrl` + `k`, `p`. Choose "pdf", and press `Enter`.
