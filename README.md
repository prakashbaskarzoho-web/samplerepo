# Zoho Payments Website

A [Hugo](https://gohugo.io/) based static site powering **Zoho Payments**.
---

## Table of Contents
- [Getting Started](#getting-started)
- [Setup](#setup)
- [For New Developers](#for-new-developers)
- [Deployment](#deployment)
- [Maintanence](#maintanence)
- [Contributing Guidelines](#contributing-guidelines)

---

## Getting Started
This respository contains **[ZOHO Payments](https://www.zoho.com/payments/)** website content.

Zoho Git Access → [Join here](https://gitusercreation.csez.zohocorpin.com/)
Need to get the `zpay git` access from this [Cliq Group]()

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
- Run this command to set the npm registry.
  ```bash
  npm set registry http://cm-npmregistry/
  ```
- Install trago:
  ```bash
  npm i -g trago
  ```
  Run `sudo chown -R $USER /usr/local` if you get error: EACCES, permission denied.

---

## Setup
1. Clone repository
   ```bash
   git clone https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website.git
   ```
2. Navigate to website folder
  ```bash
   cd zohopay_website/website
   ```
3. Run `yarn` (only needed for the first time).
4. Replace the first line of /etc/hosts with the following line:
    ```bash
    127.0.0.1 localhost localhost.csez.zohocorpin.com
    ```
5. Run `trago` (or trago.cmd on Windows).

---

## For new developers

- Our websites are built using [Hugo](https://gohugo.io/), a open source static site generator. Check the documentation to understand content organization and templating.
- [Trago](https://git.csez.zohocorpin.com/zohofinance/trago) handles most aspects of our development cycle from fetching assets to running dev servers to deploying the files to local servers. It uses Gulp to automate repetitive tasks. It is highly recommended to read the documentation to understand all available options.
- Any changes to existing pages and addition of new pages should adhere to the website checklist.

---

## Deployment
- When a Merge Request is merged, it will automatically upload the files in `payments` to the local server.  
- Check the changes in [localzoho site](https://www.localzoho.com/)
- To go live, we need to initiate the deployment in this [site](https://sd.csez.zohocorpin.com/)

---

## Maintanence
- Any updates to pages such as image changes should be followed by removal of older files from local and live environments. If pages are removed, corresponding content markdown, layout file, scripts, stylesheets, images and any other unused assets should be removed.
- If a url of a web page is updated, then we need to redirect the visitors to the new url. To redirect pages in live, drop a mail to webmaster@zohocorp.com

---

## Contributing Guidelines
Follow these best practices when contributing:

- Use SVGs instead of PNG/JPG (scalable + smaller size).  
- Optimize images before committing:  
  - PNG/JPG → [TinyPNG](https://tinypng.com)  
  - SVG → [SVGOMG](https://jakearchibald.github.io/svgomg/)  
- Do not use inline styles inside `.html`. Use `.css`.  
- Use `gulp-inline-source` for inlining SVGs/CSS when necessary.  
- Use progressive images where possible.  
