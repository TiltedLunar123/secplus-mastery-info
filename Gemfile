source "https://rubygems.org"

# Pinned to the meta-gem GitHub Pages uses to build this site, so a
# local `bundle exec jekyll serve` matches what Pages will actually
# render. Bumping this is the only place plugin versions should change.
gem "github-pages", "~> 232", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
end

# Windows and JRuby do not ship with a zoneinfo database; tzinfo-data
# fills that gap so Jekyll's date filters work cross-platform.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Faster file watching on Windows during `jekyll serve --watch`.
gem "wdm", "~> 0.1.1", platforms: [:mingw, :x64_mingw, :mswin]
