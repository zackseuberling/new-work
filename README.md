<h1 align="center">new-work</h1>

<h5 align="center">✨ Discover when artists post new work</h5>

<div align="center">
  <a href="https://npmjs.org/package/new-work">
    <img src="https://img.shields.io/npm/v/new-work.svg?style=flat-square" alt="NPM Version" />
  </a>
  <a href="https://travis-ci.org/s3ththompson/new-work">
    <img src="https://img.shields.io/travis/s3ththompson/new-work/master.svg?style=flat-square" alt="Build Status" />
  </a>
  <a href="https://nodejs.org/api/documentation.html#documentation_stability_index">
    <img src="https://img.shields.io/badge/stability-experimental-orange.svg?style=flat-square" alt="Stability" />
  </a>
</div>

![screenshot](https://user-images.githubusercontent.com/970121/28145834-3ba6a1fc-672a-11e7-9323-205c6a48e68a.jpg)

## Features

**✨ Automagic**: Automatically checks artists' websites for new work. Works by looking at a site's `last-modified` HTTP header or by diffing a specific HTML element.

**📂 Organized**: Keeps track of artists in various categories via a simple YAML file with a CLI helper.

**⚡ Fast**: Fetches sites in parallel for fast and efficient updates.

## Installation

```sh
$ npm install new-work
```

## Usage

```txt
Usage: newwork <command> [options]

  Commands:
    <default>                   Run 'newwork serve'
    serve                       Scrape, update, and serve a new-work page
    build                       Scrape, update, and save a new-work page to disk
    print                       Scrape, update, and print a table to the terminal 
    add [url]                   Add an URL to your list of sites
    remove [url]                Remove an URL from your list of sites
    ls                          List all sites in your new-work page

  Available options:
    -i, --input <filename>      Input YAML file [default: ~/.newwork.yaml]
    -o, --output <filename>     Output HTML file [default: ./newwork.html]
    -l, --lockfile <filename>   Lockfile location [default: ~/.newwork.lock]
    -p, --port=<n>              Bind 'newwork serve' to a port [default: 3030]
    -h, --help                  Print usage
```

## Guide

1.  Run `newwork add <url>` to add a site to track.

1.  Confirm the site's title / the artist's name.

1.  Optionally specify a category (e.g. 'Photography').

1.  If the site returns a `last-modified` header, you're done! Otherwise, you must manually specify an HTML element to diff for updates.

1.  Open the site with a web inspector such as Chrome DevTools Elements panel. Search for an HTML element that will change when the site is updated. The could be a thumbnail on the homepage, a menu of projects, or a blog post element.

    ![guide](https://user-images.githubusercontent.com/970121/28145836-3ed2cde2-672a-11e7-8e17-cd7c2b097aed.jpg)

1.  Specify a jQuery selector that will return the chosen element. For example, a link element inside a thumbnail with the class `thumb` may be referenced by the selector `.thumb a`. Only the first matched element will be used.

1.  Repeat for additional sites.

1.  Run `newwork` or `newwork serve` to open a list of all your sites. Sites that have been changed in the last 30 days are highlighted with a "new" tag.

## JS API

TODO

## See Also

- [Hardly Everything](https://hardlyeverything.com/) - [@jondashkyle](https://github.com/jondashkyle) 🙌

## License

[MIT](https://tldrlegal.com/license/mit-license)
