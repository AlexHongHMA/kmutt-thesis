# KMUTT Thesis Template

A LaTeX thesis template for King Mongkut's University of Technology Thonburi (KMUTT) students. This template provides a complete structure and formatting that follows KMUTT thesis guidelines, ready to be customized with your own research content.

## 🎯 About This Template

This is a **sample template** created to help KMUTT students write their theses. All content has been replaced with generic placeholders (marked with `[brackets]`) that you should replace with your actual research content. The template maintains proper KMUTT formatting and structure while allowing you to focus on your research content.

## 📋 Requirements

- **LaTeX Distribution**: TeX Live 2023 or newer
- **Required Packages**: All packages are listed in `setup/packages.tex`
- **BibTeX**: For bibliography processing
- **Images**: PNG/JPG images should be placed in the `images/` directory

## 🚀 Quick Start

1. **Clone or download this template**
2. **Replace placeholder content** with your research:
   - Update `setup/metadata.tex` with your name, thesis title, advisor, etc.
   - Replace bracketed placeholders `[like this]` throughout all chapters
   - Add your own images to `images/` directory
   - Update `references.bib` with your actual references
3. **Build the document** using the compilation steps below

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
kmutt_thesis_sample/
├── main.tex                 # Main document file
├── references.bib           # Bibliography database (sample references included)
├── setup/
│   ├── packages.tex         # LaTeX packages and configuration
│   ├── formatting.tex       # Document formatting settings
│   └── metadata.tex         # Title, author, and metadata (CUSTOMIZE THIS!)
├── frontmatter/
│   ├── titlepage.tex        # Title page
│   ├── abstract.tex         # Abstract (CUSTOMIZE THIS!)
│   ├── acknowledgement.tex  # Acknowledgements (CUSTOMIZE THIS!)
│   ├── contents.tex         # Table of contents
│   ├── listtables.tex       # List of tables
│   ├── listfigures.tex      # List of figures
│   ├── listsymbols.tex      # List of symbols (CUSTOMIZE THIS!)
│   └── listabbrev.tex       # List of abbreviations (CUSTOMIZE THIS!)
├── chapters/
│   ├── chapter1.tex         # Introduction (CUSTOMIZE THIS!)
│   ├── chapter2.tex         # Literature Review (CUSTOMIZE THIS!)
│   ├── chapter3.tex         # Methodology (CUSTOMIZE THIS!)
│   ├── chapter4.tex         # Results and Discussion (CUSTOMIZE THIS!)
│   └── chapter5.tex         # Conclusion (CUSTOMIZE THIS!)
└── images/
    └── Black_Logo.jpg       # KMUTT logo (add your own images here)
```

## ✏️ Customizing the Template

### Step 1: Update Metadata
Edit `setup/metadata.tex` to include:
- Your name
- Thesis title
- Advisor name
- Department
- Submission date

### Step 2: Replace Placeholder Content
Throughout all chapters and frontmatter files, replace:
- `[YOUR NAME]` with your actual name
- `[YOUR RESEARCH TOPIC]` with your thesis title
- `[your research area]` with your field of study
- `[Advisor Title and Name]` with your advisor's information
- All other bracketed placeholders with your content

### Step 3: Add Your Research Content
- Write your actual research content in each chapter
- Add your methodology, results, analysis
- Include your own figures and tables
- Update the literature review with relevant sources

## 🖼️ Adding Images

1. Place image files in the `images/` directory
2. Use standard formats: PNG, JPG, PDF
3. Reference images in LaTeX using:
   ```latex
   \begin{figure}[htbp]
       \centering
       \includegraphics[width=0.8\textwidth]{images/your_image.png}
       \caption{Your caption here}
       \label{fig:your_label}
   \end{figure}
   ```

**Note**: The template includes commented examples in Chapter 4 showing how to add figures.

## 📚 Bibliography Management

1. Replace sample references in `references.bib` with your actual sources
2. Cite references in text using `\cite{reference_key}`
3. Bibliography style is set to IEEE (`ieeetr`)

Example BibTeX entry:
```bibtex
@article{yourkey2024,
  title={Your Article Title},
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
5. **Backup**: Keep regular backups of your work
6. **Incremental Writing**: Write and compile frequently to catch errors early

## 📋 Checklist for Students

Before submitting your thesis, ensure you have:
- [ ] Replaced ALL bracketed placeholders with your content
- [ ] Updated metadata.tex with your information
- [ ] Written your actual research content in all chapters
- [ ] Added your own references to references.bib
- [ ] Included your own figures and tables
- [ ] Proofread all content for accuracy
- [ ] Verified all citations and references work
- [ ] Checked that the document compiles without errors

## 🤝 Contributing

If you find improvements to this template or formatting issues, feel free to contribute back to help future KMUTT students.

## 📝 License

This thesis template is for academic use at KMUTT. The template structure and formatting are provided as-is to help students with their thesis writing. 