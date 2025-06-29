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

### Header/Footer Customization

Customize the header and footer in the main `.tex` file:

```latex
\makecvheader[C] % C for center, L for left, R for right
\makecvfooter{Left text}{Center text}{Right text}
```

## License

This template is based on the [Awesome CV](https://github.com/posquit0/Awesome-CV) project by Claud D. Park, available under the Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0).

