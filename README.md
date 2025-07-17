# KMUTT-THESIS-LATEX-FORMAT

A LaTeX thesis template for King Mongkut's University of Technology Thonburi (KMUTT) students. This template provides a complete structure and formatting that follows KMUTT thesis guidelines, ready to be customized with your own research content.

## 🎯 About This Template

This is a **sample template** created to help KMUTT students write their theses. All content has been replaced with generic placeholders (marked with `[brackets]`) that you should replace with your actual research content. The template maintains proper KMUTT formatting and structure while allowing you to focus on your research content.

## 📋 Requirements

- **LaTeX Distribution**: TeX Live 2023 or newer
- **Required Packages**: All packages are listed in `setup/packages.tex`
- **BibTeX**: For bibliography processing
- **Images**: PNG/JPG images should be placed in the `images/` directory

## 🛠️ Installation Guide

### For Windows Users (Recommended Setup)

This guide shows how to set up a complete LaTeX environment on Windows using WSL (Windows Subsystem for Linux), which provides better compatibility and performance for LaTeX compilation.

#### Step 1: Install Windows Subsystem for Linux (WSL)

1. **Enable WSL feature:**
   - Open PowerShell as Administrator
   - Run the following command:
   ```powershell
   wsl --install
   ```
   - This installs WSL2 with Ubuntu as the default distribution
   - Restart your computer when prompted

2. **Set up Ubuntu:**
   - After restart, Ubuntu will automatically open and complete installation
   - Create a username and password when prompted
   - Update the system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

#### Step 2: Install TeX Live in WSL

1. **Install TeX Live (Full installation recommended):**
   ```bash
   sudo apt install texlive-full -y
   ```
   - This installs the complete TeX Live distribution (~4GB)
   - For a smaller installation, use `texlive-latex-extra` instead

2. **Verify installation:**
   ```bash
   pdflatex --version
   bibtex --version
   ```

#### Step 3: Install VS Code and LaTeX Workshop Extension

1. **Install VS Code on Windows:**
   - Download from [https://code.visualstudio.com/](https://code.visualstudio.com/)
   - Install with default settings

2. **Install WSL extension:**
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Search for "WSL" and install the official Microsoft WSL extension

3. **Install LaTeX Workshop extension:**
   - In VS Code Extensions, search for "LaTeX Workshop"
   - Install the LaTeX Workshop extension by James Yu

4. **Connect to WSL:**
   - Open VS Code
   - Press `Ctrl+Shift+P` and type "WSL: Connect to WSL"
   - VS Code will now run in WSL environment

#### Step 4: Clone and Open the Project

1. **Navigate to your home directory in WSL:**
   ```bash
   cd ~
   ```

2. **Clone or download this thesis template:**
   ```bash
   git clone [your-repository-url] kmutt_thesis
   cd kmutt_thesis
   ```

3. **Open in VS Code:**
   ```bash
   code .
   ```

### For Linux Users

#### Install TeX Live
```bash
# Ubuntu/Debian
sudo apt install texlive-full -y

# Fedora
sudo dnf install texlive-scheme-full -y

# Arch Linux
sudo pacman -S texlive-most texlive-bibtexextra
```

#### Install VS Code and LaTeX Workshop
```bash
# Download and install VS Code from official website
# Then install LaTeX Workshop extension through VS Code Extensions
```

### For macOS Users

#### Install TeX Live (MacTeX)
1. Download MacTeX from [https://www.tug.org/mactex/](https://www.tug.org/mactex/)
2. Run the installer (requires ~4GB disk space)

#### Install VS Code and LaTeX Workshop
1. Download VS Code from [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Install LaTeX Workshop extension

### VS Code Configuration for LaTeX

After installing LaTeX Workshop, VS Code will automatically:
- Detect `.tex` files and provide syntax highlighting
- Offer auto-compilation on save
- Provide PDF preview in VS Code
- Show compilation errors and warnings

**Recommended VS Code Settings for LaTeX:**
```json
{
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux", "*.bbl", "*.blg", "*.idx", "*.ind", "*.lof", 
        "*.lot", "*.out", "*.toc", "*.acn", "*.acr", "*.alg", 
        "*.glg", "*.glo", "*.gls", "*.ist", "*.fls", "*.log", 
        "*.fdb_latexmk", "*.synctex.gz"
    ]
}
```

Add these settings to your VS Code settings.json (File → Preferences → Settings → Open JSON).

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

### Step 1: Configure Setup Files

The `setup/` folder contains essential configuration files that must be customized:

#### `setup/metadata.tex` - **MUST CUSTOMIZE**
This file contains your thesis metadata. Replace ALL placeholders:

```latex
% Student Information
\newcommand{\studentname}{[YOUR FULL NAME]}
\newcommand{\studentid}{[YOUR STUDENT ID]}

% Thesis Information
\newcommand{\thesistitle}{[YOUR THESIS TITLE]}
\newcommand{\thesistitleth}{[YOUR THESIS TITLE IN THAI]}
\newcommand{\degree}{[YOUR DEGREE e.g., Master of Science]}
\newcommand{\degreeth}{[YOUR DEGREE IN THAI]}
\newcommand{\major}{[YOUR MAJOR e.g., Computer Science]}
\newcommand{\majorth}{[YOUR MAJOR IN THAI]}

% Faculty and University
\newcommand{\faculty}{[YOUR FACULTY]}
\newcommand{\facultyth}{[YOUR FACULTY IN THAI]}
\newcommand{\university}{King Mongkut's University of Technology Thonburi}
\newcommand{\universityth}{มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าธนบุรี}

% Advisory Committee
\newcommand{\advisor}{[Advisor Title and Name]}
\newcommand{\advisorth}{[Advisor Name in Thai]}
\newcommand{\coadvisor}{[Co-advisor if any, or remove this line]}

% Submission Information
\newcommand{\submitmonth}{[MONTH]}
\newcommand{\submityear}{[YEAR]}
```

#### `setup/packages.tex` - Usually no changes needed
Contains all required LaTeX packages. Only modify if you need additional packages for your research.

#### `setup/formatting.tex` - Usually no changes needed
Contains document formatting settings (margins, fonts, spacing). Follows KMUTT guidelines.

### Step 2: Customize Front Matter

The `frontmatter/` folder contains pages that appear before your main content. **All files need customization:**

#### `frontmatter/abstract.tex` - **MUST CUSTOMIZE**
Replace the entire content with your actual abstract:
- Write a concise summary of your research (typically 150-300 words)
- Include research objectives, methodology, key findings, and conclusions
- Available in both English and Thai versions

#### `frontmatter/acknowledgement.tex` - **MUST CUSTOMIZE**
Write your personal acknowledgements:
- Thank your advisor, committee members, family, friends
- Acknowledge funding sources, institutions, or organizations
- Keep it professional and heartfelt

#### `frontmatter/listsymbols.tex` - **CUSTOMIZE IF NEEDED**
Add mathematical symbols and notations used in your thesis:
```latex
\begin{longtable}{cl}
$\alpha$ & Alpha coefficient \\
$\beta$ & Beta parameter \\
$\sigma$ & Standard deviation \\
% Add your symbols here
\end{longtable}
```

#### `frontmatter/listabbrev.tex` - **CUSTOMIZE IF NEEDED**
Add abbreviations and acronyms used in your thesis:
```latex
\begin{longtable}{ll}
AI & Artificial Intelligence \\
ML & Machine Learning \\
API & Application Programming Interface \\
% Add your abbreviations here
\end{longtable}
```

#### Auto-generated files (usually no changes needed):
- `titlepage.tex` - Uses metadata from `setup/metadata.tex`
- `contents.tex` - Table of contents (auto-generated)
- `listtables.tex` - List of tables (auto-generated)
- `listfigures.tex` - List of figures (auto-generated)

### Step 3: Replace Placeholder Content
Throughout all chapters and frontmatter files, replace:
- `[YOUR NAME]` with your actual name
- `[YOUR RESEARCH TOPIC]` with your thesis title
- `[your research area]` with your field of study
- `[Advisor Title and Name]` with your advisor's information
- All other bracketed placeholders with your content

### Step 4: Add Your Research Content
- Write your actual research content in each chapter
- Add your methodology, results, analysis
- Include your own figures and tables
- Update the literature review with relevant sources

### Quick Customization Checklist

**Essential Files to Customize:**
- [ ] `setup/metadata.tex` - Your personal and thesis information
- [ ] `frontmatter/abstract.tex` - Your research abstract
- [ ] `frontmatter/acknowledgement.tex` - Your acknowledgements
- [ ] `frontmatter/listsymbols.tex` - Your mathematical symbols (if any)
- [ ] `frontmatter/listabbrev.tex` - Your abbreviations (if any)
- [ ] All chapter files (`chapters/chapter1.tex` through `chapter5.tex`)
- [ ] `references.bib` - Your actual references

**Files that auto-update:**
- Table of contents, list of figures, list of tables (generated automatically)
- Title page (uses information from `metadata.tex`)

**Tip:** Start with `setup/metadata.tex` first, as this information is used throughout the document!

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
