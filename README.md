# Awesome CV - LaTeX Resume Template

## Overview

This repository contains a customized implementation of the Awesome CV LaTeX template for creating professional resumes, CVs, and cover letters. The template provides a clean, modern design with extensive customization options.

## Customization Guide

### Document Structure

The project is organized into modular components for easy customization:

- `resume.tex`, `cv.tex`, `coverletter.tex`: Main entry point files
- `awesome-cv.cls`: Core class file defining the document structure and styling
- `resume/`, `cv/`: Directories containing section files

### Customizing Your Resume

#### 1. Personal Information

Edit the personal information section in your main `.tex` file:

```latex
\name{First}{Last}
\address{Street, City, Country}
\mobile{(+00) 0000000000}
\email{name@example.com}
\github{username}
\linkedin{username}
```

Additional optional fields include:
- `\homepage{url}`
- `\gitlab{username}`
- `\stackoverflow{id}{name}`
- `\twitter{@username}`
- `\skype{username}`

#### 2. Document Styling

The template offers several color schemes that can be changed in the main `.tex` file:

```latex
% Available colors: awesome-emerald, awesome-skyblue, awesome-red, 
% awesome-pink, awesome-orange, awesome-nephritis, awesome-concrete, awesome-darknight
\colorlet{awesome}{awesome-skyblue}
```

You can also define custom colors:

```latex
\definecolor{awesome}{HTML}{CA63A8}
```

#### 3. Section Content

Each section of the resume is stored in a separate `.tex` file in the `resume/` directory:

- `experience.tex`: Work history
- `education.tex`: Academic background
- `skills.tex`: Technical skills
- `interests.tex`: Personal interests
- Additional optional sections: `summary.tex`, `honors.tex`, `presentation.tex`, etc.

To add or remove sections, modify the imports in your main `.tex` file:

```latex
\input{resume/summary.tex}
\input{resume/experience.tex}
\input{resume/skills}
\input{resume/education.tex}
```

#### 4. Entry Formatting

Work experience entries use the `\cventry` command:

```latex
\cventry
  {Job Title} % Position
  {Company Name} % Organization
  {Location} % Location
  {Date Range} % Date(s)
  {
    \begin{cvitems} % Description(s) of tasks/responsibilities
      \item {Description 1}
      \item {Description 2}
    \end{cvitems}
  }
```

Skills can be formatted using the `\cvskill` command:

```latex
\begin{cvskills}
  \cvskill{Category}{Skill1\hspace{2mm}Skill2\hspace{2mm}Skill3}
\end{cvskills}
```

## Compilation Guide

### Requirements

- A full TeX distribution (TeX Live recommended)
- XeLaTeX compiler
- The following fonts (included in the `fonts/` directory):
  - Source Sans Pro
  - Roboto
  - Font Awesome

### Compilation Steps

1. **Generate Resume PDF:**
   ```bash
   xelatex resume.tex
   ```

2. **Generate CV PDF (optional):**
   ```bash
   xelatex cv.tex
   ```

3. **Generate Cover Letter PDF (optional):**
   ```bash
   xelatex coverletter.tex
   ```

### Troubleshooting

- **Font Issues**: Ensure the fonts are properly installed or available in the `fonts/` directory
- **Compilation Errors**: Run XeLaTeX with the `--shell-escape` flag if needed
- **PDF Viewing**: Some PDF viewers may need to be closed and reopened to see changes

## Advanced Customization

### Custom Sections

Create new section files in the `resume/` directory and include them in your main `.tex` file.

### Layout Adjustments

Modify page margins in the main `.tex` file:

```latex
\geometry{left=1.4cm, top=.8cm, right=1.4cm, bottom=1.8cm, footskip=.5cm}
```

# Professional LaTeX Resume Template

A clean, modern resume template built with LaTeX, forked from [posquit0/Awesome-CV](https://github.com/posquit0/Awesome-CV) and customized for professional use.

## Features

- Clean, modern design
- Easy customization
- Multiple sections (Experience, Education, Skills, etc.)
- Support for profile picture
- Print-friendly layout
- Mobile-responsive PDF output

## Prerequisites

Before you begin, ensure you have the following installed:

- A LaTeX distribution (TeX Live, MiKTeX, or MacTeX)
- XeLaTeX (included in most LaTeX distributions)
- Fonts (Roboto and FontAwesome are included in the `fonts/` directory)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/your-resume.git
cd your-resume
```

### 2. Install Dependencies

#### For Ubuntu/Debian:
```bash
sudo apt-get install texlive-xetex texlive-fonts-extra
```

#### For macOS (using Homebrew):
```bash
brew install --cask mactex-no-gui
```

#### For Windows (using MiKTeX):
Download and install [MiKTeX](https://miktex.org/download)

### 3. Customize Your Resume

Edit the following files to customize your resume:

- `resume.tex` - Main resume document
- `resume/` directory contains:
  - `summary.tex` - Your professional summary
  - `experience.tex` - Work experience
  - `education.tex` - Education background
  - `skills.tex` - Skills and expertise
  - `projects.tex` - Personal or professional projects
  - `interests.tex` - Personal interests (optional)

### 4. Update Your Profile Picture

Replace `profile.png` with your own square profile picture (recommended size: 800x800px).

## Compiling Your Resume

### Using Command Line

```bash
xelatex resume.tex
```

Or use the provided Makefile (if available):

```bash
make
```

### Using LaTeX Editors

1. Open `resume.tex` in your preferred LaTeX editor (e.g., TeXstudio, Overleaf, VSCode with LaTeX Workshop)
2. Set the compiler to XeLaTeX
3. Compile the document

## Customization

### Changing Colors
Edit the `awesome-cv.cls` file to change the color scheme. Look for the `% Colors` section.

### Header/Footer Customization

Customize the header and footer in the main `.tex` file:

```latex
\makecvheader[C] % C for center, L for left, R for right
\makecvfooter{Left text}{Center text}{Right text}
```

### Adding New Sections
1. Create a new `.tex` file in the `resume/` directory
2. Add content using the provided LaTeX commands
3. Include it in `resume.tex` using `\input{resume/yourfile.tex}`

## Tips

- Keep your resume concise (1-2 pages)
- Use action verbs to describe your experience
- Quantify achievements when possible
- Proofread carefully before finalizing

## License

This repository is dual-licensed, following the requirements of the original Awesome-CV project:

### 1. `awesome-cv.cls`
This file is licensed under the **LaTeX Project Public License (LPPL) v1.3c**.
See <https://www.latex-project.org/lppl/> for the full license text.

### 2. All `.tex` Files and Content Files
(resume.tex, cv.tex, coverletter.tex, and all files in `resume/`, `cv/`)
These files are licensed under the **Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)**.
See <https://creativecommons.org/licenses/by-sa/4.0/> for the full license text.

### Attribution
This repository is derived from:
- [Awesome-CV](https://github.com/posquit0/Awesome-CV) by Claud D. Park

Please retain this notice and the original license texts when redistributing or modifying this repository.
