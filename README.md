# MiniScribe Privacy Policy Site (GitHub Pages)

This folder contains a ready-to-publish static site for your privacy policy, designed to be hosted as an independent GitHub Pages project (separate from your existing user/site page).

What’s included
- docs/index.md — your privacy policy content
- .github/workflows/pages.yml — GitHub Actions workflow to publish docs/ to Pages

How to publish as an independent site
1) Create a new GitHub repository (suggested name: miniscribe-privacy)
   - Public repository recommended for easy access by Play Console reviewers
   - Do not initialize with a README/license; we’ll push the existing files

2) Push this folder’s contents to the new repo root
   Using PowerShell from this privacy_site directory:
   
   # Option A: Using Git (no gh CLI)
   git init
   git branch -M main
   git add .
   git commit -m "Initial privacy policy site"
   git remote add origin https://github.com/<YOUR_USERNAME>/<YOUR_REPO>.git
   git push -u origin main

   # Option B: If you have GitHub CLI (gh) installed and authenticated
   gh repo create <YOUR_REPO> --public --source . --remote origin --push

3) Enable GitHub Pages
   - For most accounts, the included workflow will auto-configure Pages
   - If needed: Repository → Settings → Pages → Build and deployment → Source: GitHub Actions

4) Get the site URL
   - After the workflow runs, the URL will appear in the Actions logs and under Settings → Pages
   - Typical format: https://<YOUR_USERNAME>.github.io/<YOUR_REPO>/

5) Update Play Console
   - App content → Privacy policy: paste the site URL from step 4 (you can link directly to / if the policy is the homepage)

6) Optional customization
   - Edit docs/index.md to update contact email or styling
   - Add a favicon or CSS: place assets in docs/ and link them from index.md

Notes
- The site deploys from docs/ on the default branch via GitHub Actions
- To revise the policy later, edit docs/index.md and push to main; the site updates automatically
- You can also host this on a custom domain by adding a docs/CNAME file and configuring DNS

