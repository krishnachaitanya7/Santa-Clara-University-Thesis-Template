# Santa Clara University Thesis Template

A LaTeX template for writing theses and dissertations at Santa Clara University. It follows the formatting requirements (double spacing, title page layout, front matter ordering, etc.) so you can focus on the writing instead of the styling.

## Getting Started

1. Clone or download this repository.
2. Open [Thesis.tex](Thesis.tex) and fill in the metadata at the top — name, ORCID, email, title, department, degree, submission date, keywords, etc.
3. Build with `pdflatex` → `bibtex` → `pdflatex` → `pdflatex` (or use `latexmk`). Any modern TeX distribution (TeX Live, MacTeX, MiKTeX) and editor (Overleaf, TeXstudio, VS Code + LaTeX Workshop) will work.

## Repository Layout

- [Thesis.tex](Thesis.tex) — the main entry point. Edit metadata here and `\include` your chapters.
- [FrontMatter/](FrontMatter/) — title pages, abstract, acknowledgements, dedication, copyright, nomenclature.
- [ChapterIntro/](ChapterIntro/) — example chapter folder containing [Intro.tex](ChapterIntro/Intro.tex).
- [Appendix/](Appendix/) — appendix sources, including code listings and large tables.
- [BibTeX/](BibTeX/) — `.bib` files and bibliography styles. Add your references to [library.bib](BibTeX/library.bib).
- [LaTeX/](LaTeX/) — shared packages, layout, and custom commands. You usually don't need to touch these.

## Adding a New Chapter

It's easiest to keep each chapter in its own folder with its own `.tex` file. That way figures, sub-files, and chapter-specific assets stay together.

1. Create a new folder at the repo root, e.g. `ChapterMethods/`.
2. Add a `.tex` file inside, e.g. `ChapterMethods/Methods.tex`. Start the file with the magic comment below so editors (TeXstudio, VS Code, TeXShop, etc.) know to build the main thesis file rather than the chapter in isolation:

   ```latex
   %!TEX root = ../Thesis.tex
   \chapter{Methods}
   ```

3. Include it from [Thesis.tex](Thesis.tex) alongside the other chapters:

   ```latex
   \include{ChapterIntro/Intro}
   \include{ChapterMethods/Methods}
   ```

Use [ChapterIntro/](ChapterIntro/) as a reference for the structure.

## Contributing

Contributions are welcome. If you'd like to fix a bug, improve the formatting, or add a feature, please open a pull request. For larger changes, opening an issue first to discuss the idea is appreciated.

## License

This template is licensed under [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/). See [LICENSE.txt](LICENSE.txt) for details.
