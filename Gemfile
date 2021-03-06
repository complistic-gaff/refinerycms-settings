source 'https://rubygems.org'

gemspec

gem 'json'
gem 'protected_attributes'
gem 'refinerycms', github: 'refinery/refinerycms', branch: 'master'
gem 'refinerycms-i18n', github: 'refinery/refinerycms-i18n', branch: 'master'

gem 'friendly_id-globalize', github: 'norman/friendly_id-globalize', branch: 'master'
gem 'globalize'
gem 'paper_trail', github: 'airblade/paper_trail', branch: 'master'
gem 'awesome_nested_set', github: 'collectiveidea/awesome_nested_set', branch: 'master'

group :test do
  gem 'refinerycms-testing', github: 'refinery/refinerycms', branch: 'master'
  gem 'poltergeist'
  gem 'pry'
  gem 'pry-nav'
  gem 'capybara-email', '~> 2.1.2'
end

# Database Configuration
unless ENV['TRAVIS']
  gem 'activerecord-jdbcsqlite3-adapter', platform: :jruby
  gem 'sqlite3', platform: :ruby
end

if !ENV['TRAVIS'] || ENV['DB'] == 'mysql'
  gem 'activerecord-jdbcmysql-adapter', platform: :jruby
  gem 'jdbc-mysql', '= 5.1.13', platform: :jruby
  gem 'mysql2', platform: :ruby
end

if !ENV['TRAVIS'] || ENV['DB'] == 'postgresql'
  gem 'activerecord-jdbcpostgresql-adapter', platform: :jruby
  gem 'pg', platform: :ruby
end

# Refinery/rails should pull in the proper versions of these
gem 'sass-rails', '~> 4.0.0'
gem 'coffee-rails', '~> 4.0.0'

# Load local gems according to Refinery developer preference.
if File.exist? local_gemfile = File.expand_path('../.gemfile', __FILE__)
  eval File.read(local_gemfile)
end
