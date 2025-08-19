Home page
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/books/performance.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/books/best-practices.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/books/accessibility.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/books/seo.svg">

Pricing page
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/pricing/performance.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/pricing/best-practices.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/pricing/accessibility.svg" >
<img src="https://master.zbooks-cent7-64-3.csez.zohocorpin.com:9090/lhr/pricing/seo.svg">

## Zoho Books Website
This respository contains **[ZOHO Books](https://www.zoho.com/books/)** website content.  [IDC UPDATES](https://git.csez.zohocorpin.com/zohofinance/zohobooks_website/wikis/idc-updates-change-log-2018)

### Join Git

> Use this [link](http://integ-hm4:9091/login) to join in git..


## Getting Started

* Download [Node](https://nodejs.org/en/download)
* Run `git --version` in your terminal. If you see something like `Command not found`, download [git](https://git-scm.com/download).
* Download [Yarn](https://yarnpkg.com)
* Set npm registry with `npm set registry http://cm-npmregistry/`.
* Install trago with `npm i -g trago`. Run `sudo chown -R $USER /usr/local` if you get error: EACCES, permission denied.


### Setting up on Windows
After performing the steps in the Getting Started section, do the following:

* Download [Mercurial for Windows](https://bitbucket.org/tortoisehg/files/downloads/tortoisehg-4.4.1-x64.msi)
* Use trago by calling `trago.cmd` from your command prompt.

### Running the server
* Clone the repository by typing `git clone https://git.csez.zohocorpin.com/zohofinance/zohobooks_website`.
* Go into the cloned repository by typing `cd zohobooks_website`.
* Run `yarn`(only needed for the first time).
* Replace the first line of `/etc/hosts` with the following line:
```
127.0.0.1 localhost localhost.csez.zohocorpin.com
``` 
* Run `trago`(or `trago.cmd` on Windows).

### For new developers
* Our websites are built using [Hugo](https://gohugo.io/), a open source static site generator. Check the [documentation](https://gohugo.io/documentation/) to understand content organization and templating.
* [Trago](https://git.csez.zohocorpin.com/zohofinance/trago) handles most aspects of our development cycle from fetching assets to running dev servers to deploying the files to local servers. It uses [Gulp](https://gulpjs.com/) to automate repetitive tasks. It is highly recommended to read the [documentation](https://git.csez.zohocorpin.com/zohofinance/trago/blob/master/README.md) to understand all available options.
* Any changes to existing pages and addition of new pages should adhere to the [website checklist](https://git.csez.zohocorpin.com/zohofinance/zohobooks_website/wikis/Development-Checklist).

### To deploy
* Accepting a Merge Request will automatically upload all the files in `accounting-software, ae, au, books, ca, cpa, in, kw, lp, om, qa, sa, uk, us` to local.
* Check the changes in `https://www.localzoho.com/`
* Before moving into live, check if there are any broken links and fix them. Use this [link](http://cmsmanager.zohocorp.com/link.php) to check the broken links.
* To update in live, mail the list of files to be updated to the respective [WEBSITE COORDINATOR](https://git.csez.zohocorpin.com/zohofinance/zohofinance_website/wikis/website-coordinators). The list of modified files will be available in the build trace of the `deployMasterToStaging` task.
* [Wiki](git/zohofinance/zohobooks_website/wikis/idc-update) will be automatically updated on merging an MR. Check that it has been updated correctly.

### Lighthouse Audit
* For every Master pipeline Lighthouse audit task will run for Home and Pricing pages.
* To run Lighthouse audit for any other pages, create a pipeline manually for the respective branch and pass a variable with name `link` and its value like:
`/in/books/accountant/` in case of [accountant](https://www.zoho.com/in/books/accountant/) page and give comma(,) separated values in case of multiple pages.

### Maintanence
* Any updates to pages such as image changes should be followed by removal of older files from local and live environments. If pages are removed, corresponding content markdown, layout file, scripts, stylesheets, images and any other unused assets should be removed.
* To delete files from live, contact @vishabanathan.a or @gowtham.mk. To delete a file from local, contact a [WEBSITE COORDINATOR](https://git.csez.zohocorpin.com/zohofinance/zohofinance_website/wikis/website-coordinators)
* If a url of a web page is updated, then we need to redirect the visitors to the new url. To redirect pages in live, drop a mail to webmaster@zohocorp.com

### For website coordinators
* Use `Update to Live Finance` option in Zoho Website Manager to move the files to live.
* To update a folder, select the `Folder Update` checkbox and choose the type of files to be updated. Please note that only one folder can be updated at a time.
