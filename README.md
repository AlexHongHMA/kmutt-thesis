# KMUTT Thesis - Methane Leak Detection

A LaTeX thesis document for King Mongkut's University of Technology Thonburi (KMUTT) on methane leak detection using infrared video analysis and machine learning techniques.

## 📋 Requirements

- **LaTeX Distribution**: TeX Live 2023 or newer
- **Required Packages**: All packages are listed in `setup/packages.tex`
- **BibTeX**: For bibliography processing
- **Images**: PNG/JPG images should be placed in the `images/` directory

## 🏗️ Building the Document

### Method 1: Manual Compilation (Recommended for first-time users)

```bash
# Step 1: Initial compilation to generate auxiliary files
pdflatex main.tex

# Step 2: Process bibliography
bibtex main

# Step 3: Incorporate bibliography into document
pdflatex main.tex

# Step 4: Final compilation to resolve all cross-references
pdflatex main.tex
```

### Method 2: Automated Compilation

```bash
# Using latexmk (handles all compilation steps automatically)
latexmk -pdf main.tex

# Or using latexmk with cleanup
latexmk -pdf -c main.tex  # -c flag cleans auxiliary files after compilation
```

## 📁 Project Structure

```
thesis_latex/
├── main.tex                 # Main document file
├── references.bib           # Bibliography database
├── setup/
│   ├── packages.tex         # LaTeX packages and configuration
│   ├── formatting.tex       # Document formatting settings
│   └── metadata.tex         # Title, author, and metadata
├── frontmatter/
│   ├── titlepage.tex        # Title page
│   ├── abstract.tex         # Abstract
│   ├── acknowledgement.tex  # Acknowledgements
│   ├── contents.tex         # Table of contents
│   ├── listtables.tex       # List of tables
│   ├── listfigures.tex      # List of figures
│   ├── listsymbols.tex      # List of symbols
│   └── listabbrev.tex       # List of abbreviations
├── chapters/
│   ├── chapter1.tex         # Introduction
│   ├── chapter2.tex         # Literature Review/Methodology
│   ├── chapter3.tex         # Implementation
│   ├── chapter4.tex         # Results and Discussion
│   └── chapter5.tex         # Conclusion
└── images/                  # Image files (PNG, JPG)
```

## 🖼️ Adding Images

1. Place image files in the `images/` directory
2. Use standard formats: PNG, JPG, PDF
3. Reference images in LaTeX using:
   ```latex
   \includegraphics[width=\textwidth]{images/your_image.png}
   ```

## 📚 Bibliography Management

1. Add references to `references.bib` in BibTeX format
2. Cite references in text using `\cite{reference_key}`
3. Bibliography style is set to IEEE (`ieeetr`)

Example BibTeX entry:
```bibtex
@article{example2024,
  title={Example Article Title},
  author={Author, First and Author, Second},
  journal={Journal Name},
  volume={1},
  pages={1--10},
  year={2024},
  publisher={Publisher Name}
}
```

## 🛠️ Troubleshooting

### Common Issues

**1. Missing Images Error:**
```
LaTeX Error: File 'image.png' not found
```
- **Solution**: Ensure image files exist in `images/` directory with correct names

**2. Bibliography Not Showing:**
```
LaTeX Warning: Citation 'reference' undefined
```
- **Solution**: Run the complete 4-step compilation process (pdflatex → bibtex → pdflatex → pdflatex)

**3. Cross-references Not Working:**
```
LaTeX Warning: Reference 'fig:example' undefined
```
- **Solution**: Run pdflatex multiple times or use latexmk

**4. Package Errors:**
```
LaTeX Error: File 'package.sty' not found
```
- **Solution**: Install missing packages using your LaTeX distribution's package manager

### Build Artifacts

The following files are generated during compilation and can be safely deleted:
- `*.aux`, `*.bbl`, `*.blg`, `*.fdb_latexmk`, `*.fls`
- `*.lof`, `*.log`, `*.lot`, `*.out`, `*.toc`, `*.synctex.gz`

To clean build artifacts:
```bash
latexmk -c main.tex
```

## 🎓 Document Formatting

This thesis follows KMUTT formatting guidelines:
- **Paper Size**: A4
- **Font**: Times New Roman, 12pt
- **Margins**: Left 3cm, Right 3cm, Top 2.5cm, Bottom 2cm
- **Line Spacing**: 1.5 (18pt)
- **Page Numbering**: Roman numerals for front matter, Arabic for main content

## 📖 Usage Tips

1. **First Build**: Always run the complete 4-step process for first compilation
2. **Quick Edits**: For text-only changes, a single `pdflatex main.tex` is sufficient
3. **New References**: After adding citations, run the full bibliography process
4. **Version Control**: Consider adding `*.aux`, `*.log`, etc. to `.gitignore`

## 🚀 Quick Start

```bash
# Clone/download the project
cd thesis_latex

# Build the document
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex

# View the result
open main.pdf  # macOS
xdg-open main.pdf  # Linux
start main.pdf  # Windows
```

## 📝 License

This thesis template and content are for academic use at KMUTT. 