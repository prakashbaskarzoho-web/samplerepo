# Zoho Payments Website
[![Build Status](https://git.csez.zohocorpin.com/zohofinance/zohocheckout_website/badges/master/pipeline.svg)](https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website/-/commits/master)

> A [Hugo](https://gohugo.io/) based static site powering **Zoho Payments**.

---

## Table of Contents
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Folder Structure](#folder-structure-for-development)
- [Setup](#setup)
- [Fetching Third Party Files](#fetching-third-party-files)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing Guidelines](#contributing-guidelines)

---

## Getting Started
This repository contains the source code for the **Zoho Payments** website.

---

## Prerequisites
Before setting up the project, make sure you have:

- Node.js (LTS) → [Download](https://nodejs.org/en/download)  
- Yarn → install globally:  
  ```bash
  npm install -g yarn
  ```
- Git → check with:  
  ```bash
  git --version
  ```  
  If not installed, get it from [here](https://git-scm.com/download).
- Zoho Git Access → [Join here](https://gitusercreation.csez.zohocorpin.com/)

---

## Folder Structure for Development
1. Create base folder:
   ```bash
   mkdir -p ~/Home/web/setup
   ```
2. Clone repository:
   ```bash
   git clone https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website.git
   ```
3. Run setup:
   ```bash
   cd zfdotfiles
   source install.sh
   ```
   This will automatically configure environment variables and paths.
4. Add to `~/.bash_profile`:
   ```bash
   # zfdotconf
   if [ -f ~/.bashrc ]; then
     source ~/.bashrc
   fi
   ```

---

## Setup
1. Clone repository
   ```bash
   git clone https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website.git
   cd zohopay_website/website
   ```
2. Configure npm registry
   ```bash
   npm config set registry http://cm-npmregistry.csez.zohocorpin.com
   npm install -g @zoho/trago@8.0.0
   ```
3. Create `.env` file inside `/website`:
   ```env
   CMTOOLS_BUILDTOOL_AUTHTOKEN=<user_name>:<auth_token>
   ```
   - `user_name` → your Git username  
   - `auth_token` → [Generate here](https://build.zohocorp.com/jsp/generate_token.jsp)
4. Install dependencies & start development server
   ```bash
   yarn
   yarn start
   ```

---

## Fetching Third Party Files
```bash
yarn tpCheckout
```

---

## Deployment
- Auto Upload:  
  Accepting a Merge Request will automatically upload files in `payments` to the local server.  
- Manual Upload:  
  Refer to [manually-uploading-files-to-local](#manually-uploading-files-to-local) for manual deployment steps.  
- Verify Changes:  
  - Preview: [https://localzoho.com/payments](https://localzoho.com/payments)  
  - Check for broken links: [CMS Link Checker](http://cmsmanager.zohocorp.com/link.php)  
- Go Live:  
  Send the list of updated files to the person with upload access.  
- Update Changelog:  
  Record changes in the [changelog wiki](http://git/zohofinance/zohocheckout_website/wikis/).  

---

## Troubleshooting

Error: `EACCES, permission denied`

- MacOS
  ```bash
  sudo chown -R $USER /usr/local
  ```
- Linux
  ```bash
  sudo chown -R $USER /usr/lib/node_modules
  ```

---

## Contributing Guidelines
Follow these best practices when contributing:

- Use SVGs instead of PNG/JPG (scalable + smaller size).  
- Optimize images before committing:  
  - PNG/JPG → [TinyPNG](https://tinypng.com)  
  - SVG → [SVGOMG](https://jakearchibald.github.io/svgomg/)  
- Do not inline styles inside `.html`. Use `.css`.  
- Use `gulp-inline-source` for inlining SVGs/CSS when necessary.  
- Use progressive images where possible.  