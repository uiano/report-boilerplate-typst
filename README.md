# Changes from the LaTeX original

This is a port of UiA's report template from LaTeX to Typst.

1. **Bibliography** is handled at the bottom of `main.typ` instead of a separate `sources.tex` file.

2. **Images** have been moved into each relevant directory (`titlepage/` and `sections/`), since Typst treats each folder as its own module and does not support relative imports from parent directories.

3. **Bibliography format** has changed from `.bib` to the [Hayagriva YAML format](https://github.com/typst/hayagriva/blob/main/docs/file-format.md).

4. **Dependencies** are minimal. The two packages used are:
   - [codly](https://typst.app/universe/package/codly/) for code listings
   - [dashy-todo](https://typst.app/universe/package/dashy-todo/) for todos

5. **Labels** for figures, tables, and listings use `fig-`, `tab-`, `lst-` (dashes) instead of `fig:`, `tab:`, `lst:` (colons), which caused issues with Tree-sitter syntax highlighting.

6. **Citations** are prefixed with `cit-` because Typst uses `@` for both citations and cross-references, unlike LaTeX where `\cite{}` and `\ref{}` are distinct.

7. **`common.typ`** holds global variables and should be imported into every file in the project.

# Getting started

Open `common.typ` and set the `report_lang` variable to your desired language. Currently supported: `nb` (bokmål), `nn` (nynorsk), and `en` (english).
For other languages, use `grep` to find where each variable is used and replace them with literal values.

Then update the `report_`-prefixed variables under `// Titlepage variables` to control the title page content. There is no need to edit the title page directly.

# Known issues

The Norwegian and English UiA logos have different aspect ratios. This causes inconsistent title page layouts when switching between the two languages
