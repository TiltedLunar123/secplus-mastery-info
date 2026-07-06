# Contributing

This repository holds the public info page for SecPlus Mastery. It is a
static [Jekyll](https://jekyllrb.com/) site that GitHub Pages builds and
serves at `https://tiltedlunar123.github.io/secplus-mastery-info/`. There
is no application code here. The product itself lives in a separate
repository.

## How the landing page works

There is no `index.html` or `index.md` in the repo. GitHub Pages enables
the `jekyll-readme-index` plugin by default, which renders `README.md` as
the site's index page. So the README is the landing page, and editing the
README is how you change what visitors see first. Keep build and
maintenance notes out of the README for that reason. They belong here.

## Running it locally

You need Ruby and Bundler installed.

```sh
bundle install
bundle exec jekyll serve
```

The `baseurl` is set to `/secplus-mastery-info`, so the local site is at:

```
http://127.0.0.1:4000/secplus-mastery-info/
```

`Gemfile` pins the `github-pages` meta-gem to the same version Pages uses,
so a local build matches what will actually ship. That pin is the only
place plugin versions should change.

## What CI checks

`.github/workflows/pages-build.yml` runs on every push and pull request to
`main`. It builds the site with `--strict_front_matter` (so a malformed
front-matter block fails the build) and then verifies that the output
contains `sitemap.xml`, `404.html`, and an `index.html` with a `<title>`.
A green check means the site built and those pieces are present. If you
cannot build locally, open the pull request and let CI confirm the build
before merging.

## Editing rules

- Pricing and plan copy in the README must match the live product at
  https://secplusmastery.com. Check the live pricing page before changing
  any number here. This copy has drifted from the product before.
- Privacy policy and terms of service are published on the product site,
  not in this repo. Link to them, do not duplicate them.
- Repo-meta files (this file, `LICENSE`, `SECURITY.md`, the `Gemfile`) are
  excluded from the built site in `_config.yml`, so they are not served as
  raw pages. If you add another meta file, add it to that exclude list.
