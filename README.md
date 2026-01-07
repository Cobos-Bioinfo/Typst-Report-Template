# Typst Academic Template

A clean and simple Typst template for academic reports and assignments with automatic formatting, headers, and citation support.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Typst](https://img.shields.io/badge/typst-0.12.0+-orange.svg)

## Features

✨ **Clean Title Page** with customizable logo, title, author, course, and date  
📑 **Optional Table of Contents** on a separate page  
📝 **Numbered Headings** with navy blue styling (4 levels)  
📊 **Figure & Table Support** with automatic captions and numbering  
💻 **Syntax-Highlighted Code Blocks** with light background  
📚 **APA Bibliography** integration with `.bib` files  
🔗 **Smart Cross-References** - Figures display as "Fig. X"  
📄 **Auto Headers/Footers** - Author and course in header, page numbers in footer  
🎨 **Customizable** - Adjust title size and toggle table of contents

## Preview

[View Example PDF](https://github.com/Cobos-Bioinfo/Typst-Report-Template/blob/main/Demo/report-preview.pdf)


## Installation

### Option 1: Install as a Local Typst Package (Recommended)

Typst supports local packages that can be imported using `@local/...`.

Clone the repository into Typst’s local package directory:

#### Linux / macOS
```bash
git clone https://github.com/Cobos-Bioinfo/Typst-Report-Template.git \
  ~/.local/share/typst/packages/local/Typst-Report-Template/0.1.0
```

#### Windows (PowerShell)
```powershell
git clone https://github.com/Cobos-Bioinfo/Typst-Report-Template.git `
  "$env:APPDATA\typst\packages\local\Typst-Report-Template\0.1.0"
```
After this, the template can be imported from any Typst project using `@local/Typst-Report-Template`.

### Option 2: Use Directly in a Project (No Installation)

If you don’t want to install the template globally, you can also copy the repository into your project:
```
my-report/
├── report.typ
└── Typst-Report-Template/
    ├── template.typ
    └── typst.toml
```
Then import it using a relative path:
```typst
#import "Typst-Report-Template/template.typ": report
```

## Usage

### Minimal Example
```typst
#import "@local/Typst-Report-Template/template.typ": report

#show: report.with(
  title: "Lab Report 1",
  course: "BIOL 301",
  author: "Jane Smith",
)

= Introduction
Your content starts here.
```

### Full Example (TOC + Bibliography)
```typst
#import "@local/Typst-Report-Template/template.typ": report

#show: report.with(
  title: "Comprehensive Analysis of Machine Learning in Genomics",
  course: "CS 589 – Bioinformatics",
  author: "John Doe",
  logo: image("logo.png"),
  show-toc: true,
  bibliography-file: bibliography(
    "references.bib",
    title: "References",
    style: "apa",
  ),
  title-size: 22pt,
)

= Introduction
Recent advances @smith2024 have shown...

= Methods
== Data Collection
== Analysis

= Results
See @fig:results for details.

#figure(
  image("results.png", width: 80%),
  caption: [Experimental results],
) <fig:results>

= Discussion
= Conclusion
```

## Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `title` | string | `"Report Title"` | Main document title |
| `course` | string | `"Course Module"` | Course or module name (appears in header) |
| `author` | string | `"Alejandro Cobos"` | Author name (appears in header) |
| `logo` | content/none | `none` | University logo (use `image("path")` to load) |
| `show-toc` | boolean | `false` | Show table of contents on separate page |
| `bibliography-file` | content/none | `none` | Bibliography (use `bibliography("file.bib", ...)` to load) |
| `title-size` | length | `24pt` | Font size for the title on title page |

## Styling Details

### Headings
- **Level 1**: 18pt, bold, navy blue (#1e3a8a)
- **Level 2**: 14pt, bold, navy blue
- **Level 3**: 12pt, bold, navy blue
- **Level 4**: 11pt, bold, navy blue

All headings are numbered (e.g., 1., 1.1., 1.1.1.)

### Layout
- **Paper**: A4
- **Margins**: 2.5cm all sides
- **Font**: New Computer Modern (similar to Times New Roman), 11pt
- **Paragraph**: Justified with 0.65em leading

### Code Blocks
- Light gray background (#f3f4f6)
- 9pt font size
- Rounded corners
- Syntax highlighting support

### Figures & Tables
- Centered alignment
- Automatic numbering
- Figure references display as "Fig. X" instead of "Figure X"

## Tips

1. **Logo Files**: Place your logo in the same directory as your `.typ` file, or use a relative path
2. **Bibliography**: Create a `references.bib` file in the same directory for citations
3. **Images**: Keep all images in a subdirectory (e.g., `images/` or `figures/`)
4. **Title Length**: If your title is long, reduce `title-size` to 22pt or 20pt to prevent overflow
5. **Cross-References**: Label figures with `<fig:name>` and reference with `@fig:name`

## File Structure Example
```
my-report/
├── report.typ           # Your main document
├── references.bib       # Bibliography file
├── logo.png             # University logo
└── images/
    ├── chart1.png
    └── diagram.svg
```

## Requirements

- Typst 0.12.0 or later
- Works with Typst CLI, Typst web app, and VS Code Typst extension

## Troubleshooting

**"Package not found" error:**
- Verify the template is installed in the correct directory
- Check that the path includes `local/Typst-Report-Template/Demo` both `template.typ` and `typst.toml` are present

**Logo/images not showing:**
- Use `image("path")` when loading images in the template parameters
- Verify the file path is correct relative to your document
- Use forward slashes `/` in paths, even on Windows

**Bibliography not working:**
- Load bibliography with `bibliography("file.bib", title: "References", style: "apa")`
- Don't just pass the filename as a string

## Contributing

Contributions are welcome! Feel free to:
- Report bugs or issues
- Suggest new features
- Submit pull requests

## License

MIT License - See [LICENSE](LICENSE) file for details

## Author

**Alejandro Cobos**
- GitHub: [@Cobos-Bioinfo](https://github.com/Cobos-Bioinfo)
- LinkedIn: [Alejandro Cobos Filloy](https://www.linkedin.com/in/acobos-bioinformatics/)

## Acknowledgments

Built with [Typst](https://typst.app/) - A modern alternative to LaTeX

---

⭐ If you find this template useful, please consider giving it a star!
