# Unipi Beamers Template

A professional LaTeX Beamer template for the University of Pisa, inspired by the Berkeley Beamer theme.

## Features

- Light & dark themes (`\upipilight`, `\unipidark`)
- Professional typography: EB Garamond, Fira Sans, JetBrains Mono
- Automatic frame numbering and PDF presenter notes
- Reusable thank you frame command
- SVG and TikZ graphics support

## Quick Start

1. Edit `main.tex`: title, author, theme (`\unipilight` or `\unipidark`)
2. Add slides in `beamers/` directory
3. Compile:

   ```bash
   lualatex -shell-escape main.tex
   ```

## Project Structure

```
unipi-beamers/
├── main.tex                      # Main presentation
├── beamerthemeUnipi.sty          # Theme & colors
├── beamers/                      # Slide files
├── images/                       # Logo and graphics
└── readme.md
```

## Configuration

### Theme Selection

```latex
\usetheme{Unipi}
\upipilight   % Light theme (default)
\unipidark    % Dark theme
```

### Thank You Frame

```latex
\unipithankyouframe[subtitle]{Your message}
```

## Colors

| Color       | Hex     | Usage             |
| ----------- | ------- | ----------------- |
| UnipiDark   | #003A66 | Titles            |
| UnipiBlue   | #00508B | Primary, footer   |
| UnipiLight  | #1A6FA0 | Body text         |
| UnipiRed    | #8B1A00 | Error/critical    |
| UnipiGreen  | #1F6B41 | Success/positive  |
| UnipiOrange | #B35900 | Warning/attention |
| UnipiTeal   | #006B6B | Info              |
| UnipiPurple | #5B3A8B | Special category  |

## Requirements

- XeLaTeX or LuaLaTeX
- Fonts: EB Garamond, Fira Sans, JetBrains Mono (optional)

## Troubleshooting

- **Font errors**: Install missing fonts or edit `beamerthemeUnipi.sty`
- **Compilation fails**: Use XeLaTeX/LuaLaTeX with `-shell-escape` flag
- **Logo not showing**: Verify `images/marchio_unipi_orizz_white.png` exists

---

**Need help?** See `beamers/01.tex` for examples or check [Beamer docs](https://www.ctan.org/pkg/beamer).
