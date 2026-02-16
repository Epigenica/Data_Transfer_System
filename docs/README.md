# Secure File Transfer Guide

This directory contains the GitHub Pages website for the Secure File Transfer Guide using `age` encryption and OneDrive/SharePoint.

## Files

- `index.html` - Main webpage with complete guide content
- `logo.png` - Project logo displayed in the top-left corner
- `header-banner.png` - Header banner image at the top of the page
- Content is embedded directly in the HTML (based on `Instrction_SharePoint_age.md`)

## Features

- **Complete Age Encryption Guide**: Step-by-step instructions for secure file transfers
- **Floating Table of Contents**: Easy navigation through all sections
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Smooth Scrolling**: Click on TOC items for smooth navigation
- **Active Section Highlighting**: Current section is highlighted in the TOC as you scroll
- **Code Examples**: Pre-formatted code blocks with syntax highlighting
- **Security Warnings**: Highlighted security best practices and warnings

## Viewing the Page

### Locally

You can preview the page locally by opening `index.html` directly in your browser, or run a local server:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080/docs/` in your browser.

### GitHub Pages

Once GitHub Pages is enabled in the repository settings (Settings > Pages > Source: docs folder), the page will be available at:

`https://<username>.github.io/<repository-name>/`

For example: `https://epigenica.github.io/Data_Transfer_System/`

## Customization

- **Logo**: Replace `logo.png` with your own logo (recommended: 200x200px, circular design works best)
- **Header Banner**: Replace `header-banner.png` with your own banner (recommended: 1200x300px)
- **Content**: Edit the HTML content section in `index.html` to update the guide
- **Styling**: Modify the `<style>` section in `index.html` to change colors, fonts, layout, etc.
- **Table of Contents**: Update the TOC links in the HTML if you add/remove sections
