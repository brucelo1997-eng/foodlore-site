# FoodLore Website — GitHub Pages Deployment

## Quick Setup

1. **Create a new GitHub repo** named `foodlore-site` (or any name)

2. **Push this folder's contents** to the repo:
   ```bash
   cd docs/foodlore-site
   git init
   git add .
   git commit -m "Initial site: landing page, privacy policy, support"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/foodlore-site.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to repo Settings > Pages
   - Source: Deploy from a branch
   - Branch: `main` / `/ (root)`
   - Click Save

4. **Configure custom domain:**
   - In repo Settings > Pages > Custom domain, enter: `foodlore.app`
   - Check "Enforce HTTPS"

5. **Update DNS at your domain registrar:**
   Add these DNS records for `foodlore.app`:

   | Type  | Name | Value                    |
   |-------|------|--------------------------|
   | A     | @    | 185.199.108.153          |
   | A     | @    | 185.199.109.153          |
   | A     | @    | 185.199.110.153          |
   | A     | @    | 185.199.111.153          |
   | CNAME | www  | YOUR_USERNAME.github.io  |

6. **Wait 15-30 minutes** for DNS propagation and HTTPS certificate.

## Site Structure

```
index.html       — Landing page (update App Store link after launch)
privacy.html     — Privacy policy (linked from App Store Connect)
support.html     — Support/FAQ page (linked from App Store Connect)
CNAME            — Custom domain config for GitHub Pages
_config.yml      — Jekyll config (minimal)
```

## URLs After Deployment

- Landing page: https://foodlore.app
- Privacy policy: https://foodlore.app/privacy (use this in App Store Connect)
- Support: https://foodlore.app/support (use this in App Store Connect)

## After App Store Launch

Update `index.html`:
- Replace `YOUR_APP_ID_HERE` in the App Store link and meta tag with your actual App ID
- Optionally add screenshots or an app preview video
