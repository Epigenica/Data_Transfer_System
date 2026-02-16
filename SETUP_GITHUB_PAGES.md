# GitHub Pages Setup Guide

This guide will help you enable and deploy your Data Transfer System documentation using GitHub Pages.

## Prerequisites

- A GitHub account
- This repository pushed to GitHub

## Step-by-Step Setup

### 1. Push Your Repository to GitHub

If you haven't already, push this repository to GitHub:

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit your changes
git commit -m "Initial commit with GitHub Pages site"

# Add your remote repository
git remote add origin https://github.com/YOUR_USERNAME/Data_Transfer_System.git

# Push to GitHub
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** (gear icon in the top menu)
3. Scroll down and click on **Pages** in the left sidebar
4. Under **Source**, you'll see a dropdown menu:
   - Select **Deploy from a branch**
   - Choose **main** branch
   - Choose **/docs** folder
5. Click **Save**

### 3. Wait for Deployment

- GitHub will automatically build and deploy your site
- This usually takes 1-3 minutes
- You'll see a message at the top of the Pages settings with your site's URL:
  ```
  Your site is live at https://YOUR_USERNAME.github.io/Data_Transfer_System/
  ```

### 4. Verify Your Site

1. Click on the URL provided by GitHub Pages
2. You should see your Secure File Transfer Guide
3. Verify that:
   - The logo appears in the top-left corner
   - The header banner is displayed
   - The table of contents is visible on the right side
   - All sections are accessible and formatted correctly

## Troubleshooting

### Site Not Loading

- **Wait**: Initial deployment can take a few minutes
- **Check Settings**: Ensure the source is set to `main` branch and `/docs` folder
- **Check URL**: Make sure you're using the correct URL (check Pages settings)
- **Clear Cache**: Try opening the URL in an incognito/private browser window

### Images Not Displaying

- Verify that `logo.png` and `header-banner.png` exist in the `docs/` folder
- Check file names match exactly (case-sensitive)
- Ensure images were committed and pushed to GitHub

### Content Not Updating

After making changes:

```bash
# Commit your changes
git add .
git commit -m "Update content"

# Push to GitHub
git push origin main
```

Wait 1-3 minutes for GitHub Pages to rebuild the site.

### Custom Domain (Optional)

To use a custom domain:

1. In Pages settings, enter your custom domain under "Custom domain"
2. Add a `CNAME` file to the `docs/` folder containing only your domain name
3. Configure your domain's DNS settings (see GitHub's custom domain documentation)

## Updates and Maintenance

### Updating Content

1. Edit `docs/index.html` directly
2. Commit and push changes to GitHub:
   ```bash
   git add docs/index.html
   git commit -m "Update guide content"
   git push origin main
   ```

### Changing Images

1. Replace `docs/logo.png` or `docs/header-banner.png`
2. Commit and push:
   ```bash
   git add docs/*.png
   git commit -m "Update images"
   git push origin main
   ```

### Modifying Styling

1. Edit the `<style>` section in `docs/index.html`
2. Commit and push your changes

## Performance Tips

- **Optimize Images**: Keep logo.png under 100KB and header-banner.png under 500KB
- **Browser Caching**: GitHub Pages automatically handles caching headers
- **Mobile Testing**: Test your site on mobile devices for responsive design

## Security

- GitHub Pages serves sites over HTTPS automatically
- If using a custom domain, ensure HTTPS is enforced in Pages settings

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Jekyll Themes](https://pages.github.com/themes/) (if you want to use Jekyll)
- [Custom Domain Setup](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## Support

If you encounter issues:

1. Check [GitHub Status](https://www.githubstatus.com/) for service issues
2. Review the [GitHub Pages troubleshooting guide](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-jekyll-build-errors-for-github-pages-sites)
3. Check repository Settings > Pages for any error messages
