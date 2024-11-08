# Notes for theme and Customization

## _data/navigation.yml:

Contains site navigational links through a Jekyll data file.

## Pages
To better organize all of your pages you can centralize them into a single location similar to posts and collections.

Step 1: Start by placing pages (.md or .html files) into a _pages directory. Meaningfully naming files should be the goal. Avoid patterns like /about/index.md as it makes distinguishing between multiple index.md files harder.

sample-project
└── _pages/
    ├── 404.md               # custom 404 page
    ├── about.md             # about page
    └── contact.md           # contact page

Step 2: Include pages to be sure Jekyll “sees” and processes the files inside of _pages. Add include: ["_pages"] to _config.yml.
_config.yml contains about the site stuff

Step 3: Assign permalink overrides in the YAML Front Matter of each.

Examples:

filename	permalink

_pages/about.md	permalink: /about/

_pages/home.md	permalink: /

_pages/contact.md	permalink: /contact/

*Posts*:
front matter in /pages/year-archive.md

*Tags*:
front matter in /pages/tag-archive.md

*sidebar and other omnipresent features*
_config.yml

## running

bundle exec jekyll serve


runs at: http://127.0.0.1:4000//
