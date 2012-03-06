source 'http://rubygems.org'

gem 'rails', '3.2.2'
gem 'sqlite3'
gem 'json'
gem 'jquery-rails'

group :assets do
  gem 'coffee-rails'
  gem 'uglifier', '>= 1.0.3'
  if ENV['LESS_RAILS_SOURCE']
    gem 'less-rails', :path => ENV['LESS_RAILS_SOURCE']
  else
    gem 'less-rails'
  end
  if ENV['LESS_RAILS_BOOTSTRAP_SOURCE']
    gem 'less-rails-bootstrap', :path => ENV['LESS_RAILS_BOOTSTRAP_SOURCE']
  else
    gem 'less-rails-bootstrap'
  end
end



