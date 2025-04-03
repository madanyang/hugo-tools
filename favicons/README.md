# Favicon Generator Script

## Overview
This script automates the process of generating optimized favicons and icons from an SVG source file. It produces various icon sizes for different platforms, including web browsers, Progressive Web Apps (PWAs), and Microsoft Edge/Internet Explorer.

Additionally, the script:
- Detects if it is being run inside a Hugo site and suggests using `assets/icons/` as the output directory.
- Allows the user to specify an output directory or defaults to `./output/`.
- Ensures required dependencies are installed before execution.
- Optimizes both SVG and PNG outputs.
- Generates necessary manifest and configuration files for PWA and Microsoft compatibility.

## Features
- **Automatic SVG Optimization** using `scour`
- **Multi-size PNG Generation** using `Inkscape`
- **PNG Optimization** using `optipng`
- **ICO File Creation** using `ImageMagick`
- **Automatic Output Directory Selection** (Hugo assets, user prompt, or fallback)
- **Manifest & Config Generation:**
  - `manifest.json` & `site.webmanifest` for PWA support
  - `browserconfig.xml` for Microsoft Edge/IE compatibility

## Prerequisites
Ensure the following dependencies are installed before running the script:

- [`scour`](https://github.com/scour-project/scour) (SVG optimization)
- [`inkscape`](https://inkscape.org/) (PNG export from SVG)
- [`optipng`](http://optipng.sourceforge.net/) (PNG optimization)
- [`ImageMagick`](https://imagemagick.org/) (ICO generation)

## Usage

Run the script with an SVG file as input:

```bash
./favicon_generator.sh path/to/favicon.svg
```

The script will:
1. Detect if it's inside a Hugo site and suggest using `assets/icons/`.
2. If not a Hugo site, prompt the user for an output directory.
3. If no input is given, default to `./output/`.
4. Generate and optimize icons.
5. Create manifest and config files.

### Example Output Files
After running the script, the output directory will contain:

```bash
assets/icons/  # (or your chosen output directory)
├── favicon.ico
├── favicon.png
├── apple-touch-icon.png
├── icon-192.png
├── icon-512.png
├── mstile-150x150.png
├── manifest.json
├── site.webmanifest
└── browserconfig.xml
```

### Generated Files Explained
- **`favicon.ico`**: Standard favicon for browsers (includes multiple sizes)
- **`favicon.png`**: 32px PNG version of the favicon
- **`apple-touch-icon.png`**: Icon for Apple devices (180px)
- **`icon-192.png`, `icon-512.png`**: Icons for PWA use
- **`mstile-150x150.png`**: Tile icon for Microsoft Edge
- **`manifest.json` & `site.webmanifest`**: Metadata for PWA
- **`browserconfig.xml`**: Configuration file for Microsoft Edge/IE tiles

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


