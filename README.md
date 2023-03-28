#NOTE

This is a version of the docs as they existed before Zumasys removed the jbase section. As Rocket's own jbase documentation is currently giving me "not found" errors (2023/03/28), I'm hosting this. And because I want a consistent place where I can find the documentation in the future.

I may or may not make changes to the docs, based on my own experience with them.

# Zumasys Documentation

![](https://github.com/zumasys/docs/workflows/Deploy%20to%20Azure/badge.svg)

This is a [VuePress](https://vuepress.vuejs.org/) documentation application that leverages [GitHub](https://github.com) as the repository of documentation. The repository is currently hosted in the [Zumasys GitHub](https://github.com/zumasys/docs) and the app is available at [Zumasys Docs](https://docs.zumasys.com). The documentation was created by way of [HelpJuice-to-Markdown](https://github.com/itsxallwater/helpjuice-to-markdown). Search functionality is provided by [Algolia DocSearch](https://docsearch.algolia.com/docs/what-is-docsearch) which crawls the documentation every 24 hours for updating and indexing. The application itself is built and deployed as a static site hosted on Azure Storage via a GitHub action.

## Directory structure

```text
├── site
│   ├── .vuepress
│   │   ├── components
│   │   ├── dist
│   │   ├── public
│   │   ├── styles
│   │   │   ├── index.styl
│   │   │   └── palette.styl
│   │   ├── theme
│   │   │   ├── components
│   │   │   ├── layouts
│   │   │   └── index.js
│   │   ├── config.js
│   │   ├── enchaneApp.js
│   ├── accuterm (AccuTerm documentation lives here)
│   ├── customer-portal (Customer Portal documentation lives here)
│   ├── jbase (jBASE documentation lives here)
│   ├── mv-connect (MV Connect documentation lives here)
│   ├── mv-dashboard (MV Dashboard documentation lives here)
│   ├── README.md (The home page of the docs)
│   └── package.json
└── README.md (You are here!)
```

## Development Steps

To run the application locally:

> You will need to have [Node.js & npm](https://nodejs.org/en/download/) installed. You'll also need [Git](https://git-scm.com/downloads).

1. `git clone https://github.com/zumasys/docs.git`
1. `cd docs` (or whatever name you used for your git clone)
1. `cd site`
1. `npm install` (Not necessary on subsequent builds)
1. To enable all features you'll need to set up environment variables. Create `.env` (for production) and `.env.development` (for development) files in the `site` folder. Use the `.env.skel` file as your baseline (for both production and development).
   * In order to configure Search with the [Algolia DocSearch](https://docsearch.algolia.com/) you'll need to add the appropriate credentials.  

   > `cd site && code .env`

   ```dotenv
   # Environment Variables
   VUE_APP_ALGOLIA_API_KEY=MyAPIKey
   VUE_APP_ALGOLIA_INDEX_NAME=MyIndexName
   ```

   * Optionally, if you want the [Vssue](https://vssue.js.org/) plugin to work you'll have to populate the following `.env` variables in the file from step 5.

   > `cd site && code .env`

   ```dotenv
   # Environment Variables
   VUE_APP_GITHUB_CLIENT_ID=MyClientKey
   VUE_APP_GITHUB_CLIENT_SECRET=MySecretKey
   ```

1. `npm run dev`
1. When compilation completes you should see the following message

   > success [12:25:41] Build 59cc58 finished in 75022 ms!  
   > VuePress dev server listening at [http://localhost:8080/](http://localhost:8080/)

1. Open [localhost:8080](localhost:8080) in your browser.

## TODO - Contributor Guidelines

## TODO - Community Guidelines

## TODO - Contributors

. The entire [Zumasys Team](https://www.zumasys.com/about/our-people/)
. Andy Takacs ([@andytakacs](https://github.com/andytakacs))
. Mike Wright ([@itsxallwater](https://github.com/itsxallwater))
. Ryan Medina ([@ryannmedina](https://github.com/ryannmedina))
. Peter Falson ([@pfalson](https://github.com/pfalson))
. Mike Street ([@mikes-zum](https://github.com/mikes-zum))
. Pete Schellenbach ([@pschellenbach](https://github.com/pschellenbach))
. Daniel Klein ([@danielkleinad](https://github.com/danielkleinad))
. Patrick Payne ([@patrickp](https://github.com/patrickp))

## Todo List

- [ ] Add [check-md](https://github.com/ulivz/vuepress-plugin-check-md) plugin (to check for dead links in Markdown)
- [ ] Add [flowchart](https://flowchart.vuepress.ulivz.com/#install) plugin (to define flowcharts in docs)
- [ ] Add [export](https://github.com/ulivz/vuepress-plugin-export) plugin (to allow for export of all docs to PDF)
- [ ] May also need [autometa](https://github.com/webmasterish/vuepress-plugin-autometa) plugin
- [ ] Add [img lazy](https://github.com/tolking/vuepress-plugin-img-lazy) plugin (to add lazy loading for images)
- [ ] Add [back to top](https://github.com/vuejs/vuepress/tree/master/packages/%40vuepress/plugin-back-to-top) plugin (for automatic back-to-top links)
- [ ] Add [PWA](https://v1.vuepress.vuejs.org/plugin/official/plugin-pwa.html)
- [ ] Check out more on [awesome-vuepress](https://github.com/vuepressjs/awesome-vuepress)
- [ ] Convert TODOs to GitHub Issues
- [ ] Add jBASE Basic, Jabba to [Prism](https://prismjs.com/#languages)
- [ ] Clean up brand consistency (e.g. 'AccuTerm' vs 'Accuterm')
- [ ] Clean up marketing website links to docs
- [ ] Update 404 page to have featured content
- [ ] More [config](https://vuepress.vuejs.org/config/)
- [ ] More [theme config](https://vuepress.vuejs.org/theme/default-theme-config.html)
- [ ] More [customization](https://vuepress.vuejs.org/guide/markdown.html)
- [x] Add [sitemap](https://github.com/ekoeryanto/vuepress-plugin-sitemap) plugin (to allow for auto creation of sitemap.xml file)
- [x] Add sidebar links matching docs directory structure
- [x] Clean up directory structure under the Zumasys folder (i.e. AccuTerm folder -> Mobile and Web)
- [x] Clean up root directory (move docs project into sub-dir)
- [x] Pull images from HelpJuice into static assets of this project and update links
- [x] Add [Vssue](https://vssue.js.org/) plugin for comments
- [x] Add breadcrumbs/navigation trail to docs layout (not seeing a plugin or config for this so we'll do it in Vue)
- [x] Add [Google Analytics](https://v1.vuepress.vuejs.org/plugin/official/plugin-google-analytics.html) plugin or the [minimal](https://github.com/webmasterish/vuepress-plugin-minimal-analytics) version
- [x] Add [Git Log](https://vuepress.github.io/en/plugins/git-log/) plugin (to add Git data to \$page object)
- [x] Add [Algolia Search](https://community.algolia.com/docsearch/) plugin ([more docs](https://vuepress.vuejs.org/theme/default-theme-config.html#algolia-docsearch))
- [x] Add [nprogress](https://vuepress.github.io/en/plugins/nprogress/#installation) plugin (to show global page loading bar)
- [x] Add [reading progress](https://github.com/tolking/vuepress-plugin-reading-progress) plugin (to show reading progress of a document)
- [x] Add [TypeScript](https://vuepress.github.io/en/plugins/typescript/#installation) plugin (to allow use of TypeScript in VuePress `.vue` files)
- [x] Add [SEO](https://github.com/lorisleiva/vuepress-plugin-seo) plugin (for automatic SEO meta tag generation)
- [x] Add [reading time](https://github.com/darrenjennings/vuepress-plugin-reading-time) plugin (to show etsimated reading time for an article)
- [x] Add [social share](https://github.com/ntnyq/vuepress-plugin-social-share) plugin (to activate social network share icons)
- [x] Add [code copy](https://github.com/znicholasbrown/vuepress-plugin-code-copy) plugin (to allow for click-to-copy of source code)
- [ ] ~~Add redirects from old HelpJuice docs to point to new docs (to preserve SEO and avoid link rot)~~
- [ ] ~~Add [Table of Contents](https://vuepress.vuejs.org/guide/markdown.html#table-of-contents)~~
- [ ] ~~Add [Clean URLs](https://vuepress.github.io/en/plugins/clean-urls) plugin (may not be necessary with current directory/README.md structure)~~
