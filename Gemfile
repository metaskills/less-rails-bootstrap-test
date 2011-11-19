source 'http://rubygems.org'

gem 'rails', '3.1.2'
gem 'sqlite3'
gem 'json'
gem 'jquery-rails'

group :assets do
  # gem 'sass-rails',   '~> 3.1.5.rc.2'
  gem 'coffee-rails', '~> 3.1.1'
  gem 'uglifier', '>= 1.0.3'
  if ENV['LESS_RAILS_SOURCE']
    gem 'less-rails', :path => ENV['LESS_RAILS_SOURCE']
  else
    gem 'less-rails', '2.1.0'
  end
  if ENV['LESS_RAILS_BOOTSTRAP_SOURCE']
    gem 'less-rails-bootstrap', :path => ENV['LESS_RAILS_BOOTSTRAP_SOURCE']
  else
    gem 'less-rails-bootstrap', '1.4.1'
  end
end



