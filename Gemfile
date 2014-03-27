source 'https://rubygems.org'

gem 'pry'

group :lint do
  gem 'foodcritic', '~> 3.0' #wait on fix for #224
  gem 'rubocop', '~> 0.18'
  gem 'rainbow', '< 2.0'
end

group :unit do
  gem 'berkshelf',  '~> 3.0.0.beta6'
  gem 'chefspec',   '~> 3.1'
end

group :kitchen_common do
  gem 'test-kitchen', '~> 1.2'
end

group :kitchen_vagrant do
  gem 'kitchen-vagrant', '~> 0.11'
end

# group :kitchen_cloud do
#   gem 'kitchen-digitalocean'
#   gem 'kitchen-ec2'
# end

group :plugins do
  gem 'vagrant', :git => 'https://github.com/mitchellh/vagrant', :branch => 'vagrant-next'
  gem 'vagrant-rackspace', :git => 'https://github.com/maxlinc/vagrant-rackspace', :branch => 'windows'
end
