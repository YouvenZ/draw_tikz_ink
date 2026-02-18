# TikZ Drawing Packages for TexText

A comprehensive LaTeX preamble file for creating advanced diagrams, plots, and tables directly in Inkscape using the [TexText extension](https://textext.github.io/textext/).

---

## 📋 Overview

This preamble file (`drawing_packages.tex`) provides a pre-configured LaTeX environment with extensive TikZ libraries, plotting capabilities, and table formatting packages. It allows you to create publication-quality graphics and diagrams directly within Inkscape without needing to manually import packages each time.

**Key capabilities:**
- **TikZ diagrams**: Flowcharts, network diagrams, block diagrams, UML diagrams
- **PGFPlots**: Scientific plots, graphs, and data visualization
- **Professional tables**: Publication-ready tables with booktabs, colored rows, aligned numbers
- **Custom styles**: Pre-defined node styles, arrow styles, and color schemes
- **Math typesetting**: Full AMS-Math support

---

## Live demo 

<div align="center">

> 🎥 **[Watch the full tutorial here](#)** | ⭐ **Don't forget to subscribe!**

<!-- Replace VIDEO_ID with your actual YouTube video ID -->
[![Watch the Demo](https://img.youtube.com/vi/85kKPOkd9oo/maxresdefault.jpg)](https://www.youtube.com/watch?v=85kKPOkd9oo)

*Click to watch the full tutorial on YouTube*

</div>


## 🚀 Quick Start

### 1. Locate the File

The file is located at:
```
C:\Users\youve\AppData\Roaming\inkscape\extensions\textext\drawing_packages.tex
```

### 2. Use in TexText

1. Open Inkscape
2. Go to **Extensions → Tex Text**
3. In the TexText dialog, click **"Select..."** next to "Preamble file"
4. Navigate to drawing_packages.tex and select it
5. Enter your TikZ/LaTeX code in the code area
6. Click **OK**

**Example code to try:**
```latex
\begin{tikzpicture}
  \node[modern box] (A) {Start};
  \node[process, right=of A] (B) {Process};
  \node[decision, right=of B] (C) {Decision?};
  \draw[arrow] (A) -- (B);
  \draw[arrow] (B) -- (C);
\end{tikzpicture}
```

---

## 📦 What's Included

### Core Packages

| Package | Purpose |
|---------|---------|
| **TikZ** | Vector graphics and diagrams |
| **PGFPlots** | Plotting graphs and charts |
| **Booktabs** | Professional tables |
| **xcolor** | Color support with predefined schemes |
| **AMS-Math** | Mathematical typesetting |
| **graphicx** | Image inclusion |
| **subcaption** | Subfigures support |

### TikZ Libraries Loaded

- `arrows.meta` - Advanced arrow tips
- `shapes.geometric` - Rectangles, circles, diamonds, etc.
- `positioning` - Relative node positioning
- `calc` - Coordinate calculations
- `decorations` - Path decorations
- `patterns` - Fill patterns
- `backgrounds` - Layer backgrounds
- `fit` - Fitting boxes around nodes
- `matrix`, `chains`, `shadows` - Advanced layouts

---

## 🎨 Pre-Defined Styles

### Node Styles

#### Modern Boxes
```latex
\node[modern box] {Text};          % Blue rounded box
\node[accent box] {Important};     % Orange box with shadow
\node[glass box] {Transparent};    % Semi-transparent overlay
\node[card] {Card};                % Professional card style
```

#### Shapes
```latex
\node[process] {Process};          % Green circle
\node[decision] {Decision?};       % Yellow diamond
\node[terminal] {End};             % Red rounded rectangle
\node[database] {DB};              % Purple cylinder
\node[cloud node] {Cloud};         % Blue cloud shape
```

#### Special Effects
```latex
\node[gradient box] {Gradient};    % Blue gradient fill
\node[neon] {Neon};                % Cyan on black, neon style
\node[badge] {New};                % Red circular badge
```

### Arrow Styles

```latex
\draw[arrow] (A) -- (B);           % Standard arrow
\draw[thick arrow] (A) -- (B);     % Thicker arrow
\draw[double arrow] (A) -- (B);    % Bidirectional
\draw[dashed arrow] (A) -- (B);    % Dashed line
\draw[red arrow] (A) -- (B);       % Colored red
\draw[blue arrow] (A) -- (B);      % Colored blue
\draw[curved arrow] (A) to (B);    % Curved connection
\draw[flow] (A) -- (B);            % Blue flow line
\draw[data flow] (A) -- (B);       % Green dashed flow
```

### Block Diagram Styles

```latex
\node[io] {Input};                 % Input/Output trapezoid
\node[proc] {Process};             % Process rectangle
\node[subproc] {Subprocess};       % Double-border subprocess
```

### Network Diagram Styles

```latex
\node[client] {Client};            % Blue client box
\node[router] {Router};            % Orange hexagon
\node[server] {Server};            % Gray server rectangle
```

---

## 🎨 Color Palette

Pre-defined colors available:

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| `myblue` | `#2B83BA` | Primary blue |
| `mygreen` | `#5AAE61` | Success green |
| `myred` | `#D7191C` | Error/warning red |
| `bestcell` | `#FFF7BC` | Table highlight (soft yellow) |
| `headerrow` | Gray 92% | Table header background |

**Usage example:**
```latex
\node[fill=myblue, text=white] {Blue Node};
\draw[color=mygreen, thick] (0,0) -- (2,0);
```

---

## 📊 Table Examples

### Basic Professional Table

```latex
\begin{table}[h]
\centering
\begin{tabular}{lcc}
\toprule
\textbf{Method} & \textbf{Accuracy} & \textbf{Time (s)} \\
\midrule
Algorithm A & 95.2\% & 12.3 \\
Algorithm B & 97.8\% & 15.7 \\
\bottomrule
\end{tabular}
\end{table}
```

### Table with Colored Header

```latex
\begin{tabular}{lcc}
\rowcolor{headerrow}
\textbf{Parameter} & \textbf{Value} & \textbf{Unit} \\
Temperature & 25.3 & °C \\
Pressure & 1013 & hPa \\
\end{tabular}
```

### Aligned Numbers (siunitx)

```latex
\begin{tabular}{lS[table-format=2.3]}
Method & {Accuracy (\%)} \\
\midrule
A & 95.234 \\
B & 7.891 \\
\end{tabular}
```

---

## 🔧 Customization Guide

### Adding Your Own Styles

Edit `drawing_packages.tex` and add custom TikZ styles in the `\tikzset{}` sections:

```latex
% Add after line 165
\tikzset{
    mystyle/.style={rectangle, draw, fill=purple!20, text=white},
}
```

### Changing Default Colors

Modify the `\definecolor` commands (lines 73-77):

```latex
\definecolor{myblue}{HTML}{YOUR_HEX_CODE}
\definecolor{mygreen}{HTML}{YOUR_HEX_CODE}
```

### Adding More Libraries

Insert additional `\usetikzlibrary{}` commands after line 23:

```latex
\usetikzlibrary{mindmap}    % For mind maps
\usetikzlibrary{calendar}   % For calendars
```

### Adding More Packages

Insert package declarations before line 165:

```latex
\usepackage{chemfig}        % For chemical structures
\usepackage{circuitikz}     % For circuit diagrams
```

---

## 📖 Usage Examples

### Example 1: Simple Flowchart

```latex
\begin{tikzpicture}[node distance=2cm]
  \node[terminal] (start) {Start};
  \node[process, below of=start] (proc) {Process Data};
  \node[decision, below of=proc] (dec) {Valid?};
  \node[terminal, below left=of dec] (end1) {Reject};
  \node[terminal, below right=of dec] (end2) {Accept};
  
  \draw[arrow] (start) -- (proc);
  \draw[arrow] (proc) -- (dec);
  \draw[arrow] (dec) -| node[near start, above] {No} (end1);
  \draw[arrow] (dec) -| node[near start, above] {Yes} (end2);
\end{tikzpicture}
```

### Example 2: Network Diagram

```latex
\begin{tikzpicture}[node distance=3cm]
  \node[client] (c1) {Client 1};
  \node[client, below=1cm of c1] (c2) {Client 2};
  \node[router, right of=c1, yshift=-0.5cm] (r) {Router};
  \node[server, right of=r] (s) {Server};
  
  \draw[flow] (c1) -- (r);
  \draw[flow] (c2) -- (r);
  \draw[flow] (r) -- (s);
\end{tikzpicture}
```

### Example 3: PGFPlot

```latex
\begin{tikzpicture}
\begin{axis}[
    xlabel={Time (s)},
    ylabel={Temperature (°C)},
    grid=major,
    legend pos=north west
]
\addplot coordinates {(0,20) (1,25) (2,30) (3,28) (4,32)};
\addplot coordinates {(0,18) (1,22) (2,27) (3,25) (4,29)};
\legend{Sensor A, Sensor B}
\end{axis}
\end{tikzpicture}
```

### Example 4: Layered Architecture

```latex
\begin{tikzpicture}[node distance=0.5cm]
  \node[layer=blue] (ui) {UI Layer};
  \node[layer=green, below=of ui] (logic) {Business Logic};
  \node[layer=orange, below=of logic] (data) {Data Access};
  \node[layer=gray, below=of data] (db) {Database};
\end{tikzpicture}
```

---

## ⚙️ Setup & Configuration

### Making This Your Default Preamble

**Option 1: Set in TexText GUI**
1. Open TexText (**Extensions → Tex Text**)
2. Click **"Select..."** next to "Preamble file"
3. Choose drawing_packages.tex
4. TexText will remember this for future sessions

**Option 2: Modify TexText Configuration**

Edit TexText's config file to set this as default:
```
C:\Users\youve\AppData\Roaming\inkscape\extensions\textext\textext_config.json
```

Add/modify:
```json
{
  "preamble": "drawing_packages.tex"
}
```

### Creating Multiple Preamble Files

You can create specialized preamble files for different purposes:

1. Copy drawing_packages.tex to a new file:
   ```
   cp drawing_packages.tex chemistry_preamble.tex
   ```

2. Edit the new file to add domain-specific packages:
   ```latex
   \usepackage{chemfig}
   \usepackage{mhchem}
   ```

3. Select the appropriate preamble when creating diagrams

---

## 🐛 Troubleshooting

### Issue: "Package not found"

**Solution:** Some packages may not be included in your LaTeX distribution. Install missing packages:

```bash
# On Windows (MiKTeX):
mpm --install <package-name>

# On Linux/macOS (TeX Live):
tlmgr install <package-name>
```

### Issue: "TikZ style not found"

**Solution:** Ensure the style is defined in the `\tikzset{}` section. Check for typos in style names.

### Issue: Compilation timeout

**Solution:** Complex diagrams may take time. In TexText:
- Increase timeout in TexText settings
- Simplify your diagram
- Use `\usetikzlibrary{external}` for complex plots

### Issue: Font size too small/large

**Solution:** Adjust the document class or use scaling:

```latex
% In your code:
\begin{tikzpicture}[scale=1.5]
  % ...
\end{tikzpicture}
```

Or modify the preamble's `\documentclass`:
```latex
\documentclass[12pt]{article}  % Increase from default 10pt
```

---

## 📚 Resources

### Learning TikZ & PGFPlots

- **TikZ Manual**: [CTAN TikZ Documentation](https://ctan.org/pkg/pgf)
- **PGFPlots Manual**: [CTAN PGFPlots](https://ctan.org/pkg/pgfplots)
- **Visual TikZ**: [texample.net](http://www.texample.net/tikz/)
- **TikZ Community**: [tex.stackexchange.com](https://tex.stackexchange.com/questions/tagged/tikz-pgf)

### TexText Documentation

- **Official Site**: [textext.github.io/textext](https://textext.github.io/textext/)
- **Installation Guide**: [Installation Instructions](https://textext.github.io/textext/install/windows.html)
- **GitHub**: [textext/textext](https://github.com/textext/textext)

---

## 🤝 Contributing

If you create useful custom styles or find improvements:

1. Edit `drawing_packages.tex`
2. Document your additions clearly with comments
3. Test with various diagram types
4. Share your styles!

---

## 📄 License

This preamble configuration is provided as-is for use with TexText and Inkscape. The packages included are subject to their respective licenses:

- **TikZ/PGF**: LaTeX Project Public License
- **PGFPlots**: GNU General Public License v3
- **Booktabs**: LaTeX Project Public License
- **TexText**: BSD 3-Clause License

---

## 💡 Tips & Best Practices

### Performance Tips

1. **Use external images for complex plots**: Generate once, reuse
2. **Avoid too many nodes**: >50 nodes can slow compilation
3. **Simplify paths**: Use `smooth` or `bezier` instead of many points
4. **Cache results**: TexText caches compiled outputs

### Style Tips

1. **Consistent spacing**: Use `node distance` globally
2. **Color palette**: Stick to 3-5 colors for coherence
3. **Font sizes**: Keep text readable (avoid <8pt)
4. **Alignment**: Use `positioning` library for clean layouts

### Workflow Tips

1. **Test incrementally**: Build diagrams step-by-step
2. **Use comments**: Document complex calculations
3. **Version control**: Keep backup copies of preamble
4. **Template library**: Save common diagram snippets

---

## 📧 Support

For issues specific to this preamble file or TexText usage:

- **TexText Issues**: [GitHub Issues](https://github.com/textext/textext/issues)
- **TikZ Questions**: [TeX StackExchange](https://tex.stackexchange.com/)
- **Inkscape Forums**: [Inkscape Community](https://inkscape.org/community/)

---

**Version**: 1.0  
**Last Updated**: 2024  
**Compatible with**: TexText 1.0+, Inkscape 1.0+, LaTeX 2021+
