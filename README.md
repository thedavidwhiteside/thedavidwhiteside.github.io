# davidwhiteside.com

Personal site built with [Jekyll](https://jekyllrb.com/) and the
[Beautiful Jekyll](https://beautifuljekyll.com/) theme.

## Requirements

- Ruby 3.2 or newer
- Bundler 2.4 or newer
- Network access on the first build (the theme is loaded with
  `jekyll-remote-theme`)

Check your versions:

```bash
ruby -v
bundle -v
```

## Local development

Install the dependencies:

```bash
bundle install
```

Start the development server with live reload:

```bash
bundle exec jekyll serve --livereload
```

The site is available at <http://localhost:4000>. Restart the server after
changing `_config.yml`.

## Build

Create a production build:

```bash
JEKYLL_ENV=production bundle exec jekyll build --trace
```

The generated site is written to `_site/`.

## Testing

Run Jekyll's configuration and dependency checks:

```bash
bundle exec jekyll doctor
```

Serve the site in one terminal:

```bash
bundle exec jekyll serve
```

Then verify the important routes from another terminal:

```bash
curl -I http://localhost:4000/
curl -I http://localhost:4000/about/
curl -I http://localhost:4000/post/
curl -I http://localhost:4000/tags/
curl -I http://localhost:4000/cv/
curl -I http://localhost:4000/ads.txt
curl -I http://localhost:4000/sitemap.xml
curl -I http://localhost:4000/feed.xml
```

Press `Ctrl-C` in the server terminal when you are done.

You can also inspect the generated HTML directly in `_site/`. Check that:

- `/ads.txt` contains the Google Ads verification line.
- `/sitemap.xml` lists the pages and posts.
- `/feed.xml` is valid RSS.
- Post URLs still use the `/post/<slug>/` format.

### Test with Docker

If you do not have Ruby 3.2 installed locally, you can build the site in a
container:

```bash
docker run --rm -v "$PWD":/site -w /site \
  -e JEKYLL_ENV=production ruby:3.2 \
  bash -lc 'gem install bundler -v 2.4.22 --no-document && bundle _2.4.22_ install && bundle _2.4.22_ exec jekyll build --trace'
```

## Content layout

- `index.html` - home page
- `_posts/` - blog posts, shown on the home page
- `content/` - site pages and indexes:
  - `about.md` - About page at `/about/`
  - `posts.html` - Posts page at `/post/`
  - `tags.html` - tag index at `/tags/`
  - `cv.html` - `/cv/` downloads the resume, then redirects to `/about/`
  - `404.html` - not-found page at `/404.html`
- `assets/img/` - images
- `assets/files/` - downloadable files, including the resume
- `feed.xml` - RSS feed

## Deploy

Pushing to `main` builds and deploys the site to GitHub Pages with GitHub
Actions (`.github/workflows/jekyll.yml`).
