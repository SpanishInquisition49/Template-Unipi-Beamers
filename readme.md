# Unipi Beamers Template

A professional LaTeX Beamer presentation template styled with the University of Pisa (Unipi) official colors and design guidelines.

## Features

- **Official Unipi Colors**: Uses the official Unipi blue (`RGB: 0, 80, 139`) combined with complementary Berkeley colors
- **Modern Design**: Clean, professional layout with diagonal footer design and institutional logo
- **Typography**:
  - EB Garamond for titles
  - Fira Sans for body text
  - JetBrains Mono for code listings
- **Ready-to-Use**: Includes pre-configured packages for mathematics, graphics, code listings, and bibliography
- **Customizable**: Modular structure with separate slide files for easy editing
- **Presentation Features**:
  - Automatic frame numbering with total frame count
  - PDF presenter notes support (pdfpc)
  - SVG and TikZ graphics support
  - pgfplots integration for data visualization

## Requirements

- **TeX Distribution**: MiKTeX, TeX Live, or MacTeX
- **Compiler**: XeLaTeX or LuaLaTeX (required for proper font rendering)
- **Fonts** (optional but recommended):
  - EB Garamond
  - Fira Sans
  - JetBrains Mono

## Quick Start

1. **Clone or download** this repository
2. **Edit** `main.tex` to customize:
   - Title: `\title[...]{...}`
   - Subtitle: `\subtitle{...}`
   - Author: `\author{...}`
   - Language: uncomment your preferred babel language
3. **Add slides** in the `beamers/` directory:
   - Create new `.tex` files (e.g., `05.tex`)
   - Add to main.tex: `\input{beamers/05.tex}`
4. **Compile** with:

   ```bash
   lualatex -shell-escape main.tex
   # or
   xelatex -shell-escape main.tex
   ```

## Project Structure

```
unipi-beamers/
├── main.tex                      # Main presentation file
├── beamerthemeUnipi.sty          # Theme definition (colors, fonts, layout)
├── llvmlisting.sty               # Code listing customization
├── bibliography.bib              # Bibliography entries
├── beamers/
│   ├── 01.tex                    # Example slides
│   ├── 02.tex
│   ├── 03.tex
│   └── 04.tex
├── images/
│   └── marchio_unipi_orizz_white.png  # Unipi logo
└── readme.md                     # This file
```

## Configuration

### Language Support

In `main.tex`, choose your language:

```latex
% English (UK) - default
\usepackage[british]{babel}
\usepackage[autostyle]{csquotes}

% Italian
% \usepackage[italian]{babel}
% \usepackage[autostyle, italian=guillemets]{csquotes}
```

### Presentation Settings

Control presentation duration and notes:

```latex
\pdfpcsetup{
    duration=30,        % Presentation duration in minutes
    lastminutes=2,      % Alert when X minutes remain
}
```

### Title Slide

Customize the title slide information:

```latex
\title[Short Title]{Long Title}
\subtitle{Your Subtitle}
\author{Your Name}
% \date{} % Use default date or customize
```

### Footer

The default footer shows current frame / total frames. Modify in `main.tex` to customize appearance.

## Colors

The theme includes these predefined colors:

| Color                | RGB/HEX           | Usage                            |
| -------------------- | ----------------- | -------------------------------- |
| **UnipiBlue**        | RGB: 0, 80, 139   | Primary color, titles, structure |
| **BerkeleyBlue**     | #003262           | Block titles, accents            |
| **BerkeleyBlueText** | RGB: 48, 99, 126  | Body text                        |
| **BerkeleyGold**     | RGB: 193, 129, 45 | Secondary accent                 |
| **FoundersRock**     | #3B7EA1           | Alternative blue                 |

Use them in your slides:

```latex
\textcolor{UnipiBlue}{Colored text}
\colorbox{BerkeleyBlueText}{Highlighted}
```

## Custom Features

### Frame Title Variations

```latex
% Normal frame title (default)
\normalframetitle
\begin{frame}{Title}

% Smaller frame title
\smallframetitle
\begin{frame}{Title}
```

### Table Formatting

```latex
\begin{tabular}{|cc|}
\hline
\tableheadrow  % Gold row background
\tableheadcol{Header 1} & \tableheadcol{Header 2} \\
\hline
...
\end{tabular}
```

## Included Packages

### Mathematics

- `amsmath`, `amssymb` - Math symbols and equations
- `amsthm`, `mathtools` - Theorem environments and advanced math
- `bussproofs`, `proof` - Formal logic proofs
- `stmaryrd` - Semantics brackets

### Graphics & Visualization

- `tikz`, `pgfplots`, `pgfplotstable` - Diagrams and plots
- `svg`, `graphicx` - Graphics support
- `tcolorbox` - Colored boxes

### Code

- `listings` - Code highlighting
- Custom JetBrains Mono font

### Other

- `biblatex` - Bibliography (commented by default)
- `setspace` - 1.5 line spacing
- `booktabs` - Professional tables

## Customization Guide

### Add a Custom Package

Edit `main.tex` in the appropriate section (e.g., GRAPHICS & IMAGES):

```latex
\usepackage{mypackage}
```

### Define Custom Colors

In `beamerthemeUnipi.sty`, add:

```latex
\definecolor{MyColor}{RGB}{r, g, b}
% or
\definecolor{MyColor}{HTML}{RRGGBB}
```

### Create a Custom Command

In `main.tex` under CUSTOM COMMANDS:

```latex
\newcommand{\mycommand}{Your LaTeX code}
```

## Tips & Tricks

- **Code Listings**: The `\lstset` configuration supports syntax highlighting. Add language support as needed.
- **Presenter Notes**: Uncomment the `hidenotes` option in `pdfpc` to produce a pdf without notes.
- **Aspect Ratio**: The default is 16:9. Modify the documentclass if needed:

  ```latex
  \documentclass[10pt,aspectratio=4:3]{beamer}
  ```

- **SVG Images**: Use `\includesvg{filename}` for vector graphics.
- **Image Paths**: Place images in the `images/` directory; they're automatically found.

## Troubleshooting

### Font not found errors

- Install the required fonts (EB Garamond, Fira Sans, JetBrains Mono) on your system
- Alternatively, edit `beamerthemeUnipi.sty` to use available fonts

### Compilation errors

- Ensure you're using XeLaTeX or LuaLaTeX, not pdflatex
- Use the `-shell-escape` flag for proper compilation

### Logo not displaying

- Verify `images/marchio_unipi_orizz_white.png` exists and is accessible

## License

This template is adapted from the UC Berkeley Beamer theme and customized for the University of Pisa.

---

**Need help?** Check the example slides in `beamers/01.tex` through `beamers/04.tex` for common usage patterns, or refer to the [Beamer documentation](https://www.ctan.org/pkg/beamer).
