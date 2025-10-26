# STEMSeeds Domain Setup Guide

## When You Purchase Your Domain

### Step 1: Update CNAME File
1. Open the `CNAME` file in your repository
2. Remove all comments and the placeholder line
3. Add only your domain name (example: `stemseeds.org` or `www.stemseeds.org`)
4. Commit and push the change

### Step 2: Configure DNS at Your Domain Registrar

#### For Apex Domain (example.org):
Add these A records:
```
Type: A
Name: @
Value: 185.199.108.153

Type: A  
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

#### For WWW Subdomain (www.example.org):
Add this CNAME record:
```
Type: CNAME
Name: www
Value: stemseeds-nj.github.io
```

### Step 3: Update GitHub Pages Settings
1. Go to your repository settings
2. Navigate to Pages section
3. Set custom domain to your purchased domain
4. Enable "Enforce HTTPS" (after DNS propagation)

### Step 4: Update Website References
- Update `sitemap.xml` URLs to use your new domain
- Update social media links and bio links
- Update any hardcoded URLs in the HTML

### Step 5: Test and Verify
- DNS propagation can take 24-48 hours
- Test both `yourdomain.com` and `www.yourdomain.com`
- Verify SSL certificate is working
- Check that redirects work properly

### Optional: Redirect Old GitHub URL
If you want the GitHub Pages URL to redirect to your custom domain:
1. Keep the `redirect.html` file
2. GitHub Pages will automatically redirect github.io URLs to your custom domain

## Common Domain Registrars Setup

### Namecheap
1. Go to Domain List → Manage → Advanced DNS
2. Add the A records and CNAME as specified above

### GoDaddy  
1. Go to DNS Management
2. Add the A records and CNAME as specified above

### Cloudflare
1. Go to DNS settings
2. Add the A records and CNAME as specified above
3. Set proxy status to "DNS only" (gray cloud) initially

## Troubleshooting
- Use `nslookup yourdomain.com` to check DNS propagation
- Check GitHub Pages settings for any error messages
- Ensure CNAME file contains only the domain name, no protocols
- Wait 24-48 hours for full DNS propagation

## Need Help?
Check GitHub's official documentation: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site