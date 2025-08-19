# Zoho Payments Website

A [Hugo](https://gohugo.io/) based static site powering **Zoho Payments**.
---

## Table of Contents
- [Getting Started](#getting-started)
- [Folder Structure](#folder-structure-for-development)
- [Setup](#setup)
- [For New Developers](#for-new-developers)
- [Deployment](#deployment)
- [Lighthouse Audit](#lighthouse-audit)
- [Contributing Guidelines](#contributing-guidelines)

---

## Getting Started
This respository contains **[ZOHO Payments](https://www.zoho.com/payments/)** website content.

Zoho Git Access → [Join here](https://gitusercreation.csez.zohocorpin.com/)

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
- Set npm registry with npm set registry http://cm-npmregistry/.
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
   cd zohopay_website/website
   ```
2. Run `yarn` (only needed for the first time).
3. Replace the first line of /etc/hosts with the following line:
    ```bash
    127.0.0.1 localhost localhost.csez.zohocorpin.com
    ```
4. Run `trago` (or trago.cmd on Windows).

---

## For new developers

- Our websites are built using [Hugo](https://gohugo.io/), a open source static site generator. Check the documentation to understand content organization and templating.
- [Trago](https://git.csez.zohocorpin.com/zohofinance/trago) handles most aspects of our development cycle from fetching assets to running dev servers to deploying the files to local servers. It uses Gulp to automate repetitive tasks. It is highly recommended to read the documentation to understand all available options.
- Any changes to existing pages and addition of new pages should adhere to the website checklist.

---

## Deployment
- Accepting a Merge Request will automatically upload files in `payments` to the local server.  
- Check the changes in `https://www.localzoho.com/`
- Verify Changes:  
  - Preview: [https://localzoho.com/payments](https://localzoho.com/payments)  
  - Check for broken links: [CMS Link Checker](http://cmsmanager.zohocorp.com/link.php)  
- To go live, mail the list of files to be updated to the respective [WEBSITE COORDINATOR](https://git.csez.zohocorpin.com/zohofinance/zohofinance_website/wikis/website-coordinators). The list of modified files will be available in the build trace of the `deployMasterToStaging` task. 
---

## Lighthouse Audit
- For every Master pipeline Lighthouse audit task will run for Home and Pricing pages.
- To run Lighthouse audit for any other pages, create a pipeline manually for the respective branch and pass a variable with name `link` and its value like:
`/in/payments/contact-us/` in case of [contact](https://www.zoho.com/in/payments/contact-us/) page and give comma(,) separated values in case of multiple pages.

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