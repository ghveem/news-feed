# https://ghveem.github.io/news-feed/

Hello! This repo houses the code that generates my personal RSS feed. It's hosted at [https://ghveem.github.io/news-feed/](https://ghveem.github.io/news-feed/).
The code itself is non-generic and personalised to my use case, but it might serve as interesting inspiration.

## How does it work?

The project is separated into 2 components:

- **News Getter**, which is a Go application to fetch news from various RSS feeds and store them
- **News Cleaner**, which is a Go application to cleanup old news
- **News Site**, which is a [Hugo](https://gohugo.io)-based project to build the website

### Fetching news

The RSS feed is generated by the script [main.go](/news-getter/main.go). It:

1. Read a list of RSS feeds from [feeds.json](/feeds.json)
2. Iterates over them, and reads the posts from the last month and stores them in a big list of all posts

### Building the website

The News Site is built using [Hugo](https://gohugo.io).

### Hosting the website

The website is hosted by GitHub pages.

### Automation

A [GitHub Action](/.github/workflows/update-website.yml) is used to fetch the latets news, cleanup the old ones and build the website using [Hugo](https://gohugo.io) and deploy it to GitHub Pages ✨.

## Credits

This project is heavily inspired by [jamesroutley/news.routley.io](https://github.com/jamesroutley/news.routley.io) which also [wrote a blog post about this](https://routley.io/posts/bespoke-software-rss-aggregator/).