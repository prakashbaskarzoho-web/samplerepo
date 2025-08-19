+++
date = '2025-08-13T14:58:20+05:30'
title = 'README'
+++


## Zoho Payments Website [![build status](https://git.csez.zohocorpin.com/zohofinance/zohocheckout_website/badges/master/pipeline.svg)](https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website/-/commits/master)
This is a hugo static website.

## Getting Started
This respository contains the **ZOHO Payments** website source.

## Prerequisites
* Node JS -  Download latest node LTS version from [here](https://nodejs.org/en/download) and install.
* Install Yarn - `npm i -g yarn`
* Install Git - Run `git --version` in your terminal. If you see something like Command not found, download [Git](https://git-scm.com/download).
* Join Git - If you don't have an account in git. Use this link to [join](https://gitusercreation.csez.zohocorpin.com/) in git.

### Folder Structure for Development
 1. Create the folder structure: ~/Home/web/setup
 2. Clone zfdotfiles inside /setup. Command: `git clone https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website.git`
 3. Folder zfdotfiles will be created. Inside /zfdotfiles, type the command: `source install.sh`
 4. On running the above command, all the env variables, path etc will be set automatically.
 5. Create a file named `.bash_profile` in your root folder and save the following content in it:

 ```
#zfdotconf
if [ -f ~/.bashrc ]; then  
 source ~/.bashrc
fi
```

## Setup

```bash
# Create the folder structure: ~/Home/web/workspace
$ git clone https://zpaygit.csez.zohocorpin.com/zohopay/zohopay_website.git
$ cd zohopay_website/website
$ npm config set registry http://cm-npmregistry.csez.zohocorpin.com
$ npm install -g @zoho/trago@8.0.0
$ Create .env file inside /website folder and add the following content to fetch the third party packages.
  CMTOOLS_BUILDTOOL_AUTHTOKEN=<user_name>:<auth_token>
  * user_name -> your git user name
  * auth_token ->[Generate using this link](https://build.zohocorp.com/jsp/generate_token.jsp)
$ yarn
$ yarn start
```

### Fetch third party files
```bash
$ yarn tpCheckout
```

### To upload it in mirror server

* Accepting a Merge Request will automatically upload all the files in `payments` to local. To Manually upload files refer [Manually uploading files to local](#manually-uploading-files-to-local)
* Check the changes in `https://localzoho.com/payments`
* Before moving into live, check if there are any broken links and fix them. Use this [link](http://cmsmanager.zohocorp.com/link.php) to check the broken links.
* To update in live, send the list of files to be updated to the person who has the upload access.
* Update the website changes in this [changelog wiki](http://git/zohofinance/zohocheckout_website/wikis/)

## Troubleshooting

If you get error: EACCES, permission denied:

```bash
# MacOS User
$ sudo chown -R $USER /usr/local 
```

```bash
# Linux User
$ sudo chown -R $USER /usr/lib/node_modules
```

## Contributing guidelines

* `<svg>` is better than png and jpg in a lot of cases. Sprites can be made using svgs too.
* Inlining `svg` in html makes it hard to read. Use gulp-inline-source to inline them at build.
* Do not write styles in `.html` files. Thats what `.css` is for. Inline css files using gulp-inline-source if you need perf.
* Minify images with tiny-png and svg with svg-omg before using them. Progressive images are even better.

