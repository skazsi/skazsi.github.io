class NilClass
  def tainted?; false; end
  def untainted?; true; end
end

class String
  def tainted?; false; end
  def untainted?; true; end
end

source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
gem "liquid", "~> 4.0.4"
gem "tzinfo-data"
gem "csv"
gem "bigdecimal"

# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-paginate"
  gem "jekyll-sitemap"
  gem "jekyll-gist"
  gem "jekyll-feed"
  gem "jemoji"
  gem "jekyll-include-cache"
  gem "jekyll-algolia"
end

gem "webrick", "~> 1.8"
