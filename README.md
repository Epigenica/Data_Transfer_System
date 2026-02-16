# Data Transfer System

A centralized repository for documentation and implementation of the Data Transfer System (DTS), featuring a secure file transfer guide using `age` encryption and OneDrive/SharePoint.

## 📚 Documentation

The project includes a comprehensive GitHub Pages site with a complete guide for secure file transfer.

### Live Documentation
Once GitHub Pages is enabled, the documentation will be available at:
`https://<username>.github.io/Data_Transfer_System/`

## 🚀 Quick Start

### Enabling GitHub Pages

1. Go to your repository **Settings** on GitHub
2. Navigate to **Pages** in the left sidebar
3. Under **Source**, select:
   - Branch: `main` (or your default branch)
   - Folder: `/docs`
4. Click **Save**
5. Wait a few minutes for GitHub to build and deploy your site
6. Your site will be live at the URL shown on the Pages settings page

### Local Preview

To preview the documentation locally:

```bash
# Option 1: Open index.html directly in your browser
open docs/index.html

# Option 2: Run a local web server
cd docs
python3 -m http.server 8080
# Then visit http://localhost:8080 in your browser
```

## 📁 Repository Structure

```
Data_Transfer_System/
├── _config.yml                      # GitHub Pages configuration
├── README.md                        # This file
├── instruction.md                   # General instructions
├── Instrction_SharePoint_age.md    # Source content for the guide
└── docs/                            # GitHub Pages site
    ├── index.html                   # Main page with embedded content
    ├── logo.png                     # Project logo
    ├── header-banner.png            # Header banner image
    └── README.md                    # Documentation folder info
```

## 🔐 What's Included

The documentation site provides a complete guide for:

- **Installing `age` encryption tool** (macOS, Linux, Windows)
- **Generating encryption keys**
- **Encrypting files before upload**
- **Uploading to OneDrive/SharePoint** (up to 250 GB per file)
- **Securely downloading and decrypting files**
- **Multi-recipient encryption**
- **Security best practices**

## 🎨 Customization

### Update Content
- Edit the HTML content in `docs/index.html`
- Or modify `Instrction_SharePoint_age.md` and regenerate the HTML

### Change Branding
- Replace `docs/logo.png` with your logo (recommended: 200x200px)
- Replace `docs/header-banner.png` with your banner (recommended: 1200x300px)

### Modify Styling
- Edit the `<style>` section in `docs/index.html`
- Adjust colors, fonts, layout, and responsive breakpoints

### Update Site Metadata
- Modify `_config.yml` to change site title, description, and author

## 📋 Features

- ✅ **Self-contained HTML** - All content embedded, no external dependencies
- ✅ **Floating Table of Contents** - Easy navigation with active section highlighting
- ✅ **Responsive Design** - Works on all devices
- ✅ **Code Examples** - Pre-formatted code blocks with proper styling
- ✅ **Security Warnings** - Highlighted best practices and warnings
- ✅ **Smooth Scrolling** - Enhanced user experience

## 🛠️ Technologies

- HTML5
- CSS3 (responsive design)
- Vanilla JavaScript (no external libraries)
- GitHub Pages (static site hosting)

## 📝 License

This project is maintained by Epigenica.
