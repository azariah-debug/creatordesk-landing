# CreatorDesk Landing Page

A mobile-first, dark-themed landing page for CreatorDesk — an AI brand-deal manager for UGC creators and micro-influencers.

## Quick Start

Simply open `index.html` in any browser. No build step required.

## Deployment to GitHub Pages with Custom Subdomain

### Prerequisites

- A GitHub account
- A registered domain (e.g., `creatordesk.app` or `getcreatordesk.com`)
- Basic familiarity with DNS settings

### Step 1: Create a GitHub Repository

1. Go to [github.com](https://github.com) and create a new repository
2. Name it something like `creatordesk-landing`
3. Set it to **Public**
4. Do NOT initialize with a README (you'll add one separately)

### Step 2: Push Your Files

```bash
cd /Users/data/Documents/Codex/creatordesk-landing
git init
git add index.html README.md
git commit -m "Initial commit: CreatorDesk landing page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/creatordesk-landing.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. In your repository, go to **Settings** → **Pages**
2. Under "Source", select **Deploy from a branch**
3. Select **main** branch and **/ (root)** folder
4. Click **Save**

GitHub will assign a URL like: `https://YOUR_USERNAME.github.io/creatordesk-landing/`

### Step 4: Configure Custom Subdomain

#### Option A: Root domain (e.g., `creatordesk.app`)

Add the following DNS records at your domain registrar:

| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

#### Option B: Subdomain (e.g., `landing.creatordesk.app`)

Add a CNAME record:

| Type | Name | Value |
|------|------|-------|
| CNAME | landing | YOUR_USERNAME.github.io |

### Step 5: Add Custom Domain in GitHub Settings

1. In your repository, go to **Settings** → **Pages**
2. In the "Custom domain" field, enter your domain (e.g., `creatordesk.app`)
3. Check **Enforce HTTPS** (GitHub will automatically provision a certificate)

### Step 6: Wait for DNS Propagation

- DNS changes can take anywhere from a few minutes to 48 hours
- Check status in GitHub Pages settings — you should see "Your site is published at [domain]"

## Project Structure

```
creatordesk-landing/
├── index.html    # Complete landing page (single file)
└── README.md     # This file
```

## Features

- Mobile-first responsive design
- Dark theme with purple (#8B5CF6) and cyan (#06B6D4) accents
- Email capture via Formspree (no backend required)
- Smooth scroll navigation
- No external JS frameworks

## Local Development

Just open `index.html` in your browser. For a quick local server:

```bash
# Using Python
python3 -m http.server 8000

# Then visit http://localhost:8000
```

## Customization

### Formspree Setup

The form currently points to a Formspree endpoint. To set up your own:

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Create a new form
3. Replace the form `action` attribute in `index.html`:

```html
<!-- Replace this -->
<form id="beta-form" action="https://formspree.io/forms/xwpjegpn/new" method="POST">

<!-- With your formspree form URL -->
<form id="beta-form" action="https://formspree.io/forms/YOUR_FORM_ID/new" method="POST">
```

### Changing Colors

All colors are defined as CSS custom properties at the top of the `<style>` section:

```css
:root {
  --primary: #8B5CF6;
  --secondary: #06B6D4;
  --bg: #0A0A0F;
  --surface: #14141F;
  --text: #F9FAFB;
  --muted: #9CA3AF;
}
```

## Troubleshooting

**GitHub Pages not showing?**
- Ensure your repository is public
- Check that Pages is enabled in Settings
- Verify the branch being deployed contains `index.html`

**Custom domain not working?**
- Verify DNS records are correct
- Wait for propagation (up to 48 hours)
- Ensure HTTPS is enforced in GitHub Pages settings

**Formspree not receiving submissions?**
- Check that your form ID is correct
- Verify the form endpoint URL matches your Formspree dashboard
- Check spam folders

## License

MIT License — feel free to use and modify for your own project.