# Data Transfer System Documentation

This directory contains the GitHub Pages website for the Data Transfer System.

## Files

- `index.html` - Main webpage with floating table of contents
- `logo.png` - DTS logo displayed in the top-left corner
- `header-banner.png` - Header banner image at the top of the page
- Content is loaded from `../instruction.md` (in the repository root)

## Features

- **Floating Table of Contents**: Automatically generated from the instruction.md headings
- **Responsive Design**: Works on desktop and mobile devices
- **Smooth Scrolling**: Click on TOC items for smooth navigation
- **Active Section Highlighting**: Current section is highlighted in the TOC as you scroll

## Viewing the Page

### Locally

You can preview the page locally by running:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080/docs/` in your browser.

### GitHub Pages

Once GitHub Pages is enabled in the repository settings (Settings > Pages > Source: docs folder), the page will be available at:

`https://<username>.github.io/<repository-name>/`

For example: `https://epigenica.github.io/Data_Transfer_System/`

## Customization

- **Logo**: Replace `logo.png` with your own logo (recommended: 200x200px)
- **Header Banner**: Replace `header-banner.png` with your own banner (recommended: 1200x300px)
- **Content**: Edit `../instruction.md` to update the page content
- **Styling**: Modify the `<style>` section in `index.html` to change colors, fonts, etc.
