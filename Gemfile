source 'https://rubygems.org'
# if there is a super emergency and rubygems is playing up, try
#source 'http://production.cf.rubygems.org'

gem 'bootsnap', require: false, platform: :mri

def rails_master?
  ENV["RAILS_MASTER"] == '1'
end

# 如果某个环境变量 == 1 就用最新版的 Rails, 否则就用 5.1 版
if rails_master?
  gem 'arel', git: 'https://github.com/rails/arel.git'
  gem 'rails', git: 'https://github.com/rails/rails.git'
  gem 'seed-fu', git: 'https://github.com/SamSaffron/seed-fu.git', branch: 'discourse'
else
  gem 'actionmailer', '~> 5.1'
  gem 'actionpack', '~> 5.1'
  gem 'actionview', '~> 5.1'
  gem 'activemodel', '~> 5.1'
  gem 'activerecord', '~> 5.1'
  gem 'activesupport', '~> 5.1'
  gem 'railties', '~> 5.1'
  gem 'sprockets-rails'
  gem 'seed-fu' # https://github.com/mbleigh/seed-fu
end

gem 'mail', '2.7.1.rc1', require: false
gem 'mini_mime'
gem 'mini_suffix'

gem 'hiredis' # https://github.com/redis/hiredis-rb # Ruby wrapper for hiredis
gem 'redis', require:  ["redis", "redis/connection/hiredis"]
gem 'redis-namespace'

gem 'active_model_serializers', '~> 0.8.3' # https://github.com/rails-api/active_model_serializers/blob/0-10-stable/docs/general/getting_started.md

gem 'onebox', '1.8.47' # https://github.com/discourse/onebox # A gem for turning URLs into website previews

gem 'http_accept_language', '~>2.0.5', require: false 
# https://github.com/iain/http_accept_language
# helps you detect the users preferred language

gem 'ember-rails', '0.18.5'
gem 'ember-source', '2.13.3'
gem 'ember-handlebars-template', '0.7.5'
gem 'barber' # https://github.com/tchak/barber #  Handlebars precompilation

gem 'message_bus' # https://github.com/SamSaffron/message_bus
# A reliable, robust messaging bus for Ruby processes and web clients.

gem 'rails_multisite' # https://github.com/discourse/rails_multisite
# This gem provides multi-db support for Rails applications.

gem 'fast_xs', platform: :mri
# https://rubygems.org/gems/fast_xs/versions/0.8.0
# escaping text

# may move to xorcist post: https://github.com/fny/xorcist/issues/4
gem 'fast_xor', platform: :mri

gem 'fastimage'
# https://github.com/sdsykes/fastimage
# FastImage finds the size or type of an image given its uri by fetching as little as needed

gem 'aws-sdk-s3', require: false # https://rubygems.org/gems/aws-sdk-s3/versions/1.0.0.rc2
gem 'excon', require: false # https://github.com/excon/excon  # Usable, fast, simple Ruby HTTP 1.1
gem 'unf', require: false  # https://rubygems.org/gems/unf    # bring Unicode Normalization Form support to Ruby/JRuby.

gem 'email_reply_trimmer', '0.1.11'
# https://rubygems.org/gems/email_reply_trimmer/versions/0.1.8
# EmailReplyTrimmer is a small library to trim replies from plain text email.

# Forked until https://github.com/toy/image_optim/pull/149 is merged
gem 'discourse_image_optim', require: 'image_optim'
gem 'multi_json' # https://github.com/intridea/multi_json  # simply choose the fastest available JSON coder
gem 'mustache'  # https://github.com/mustache/mustache   # Logic-less Ruby templates 
gem 'nokogiri'  # https://github.com/sparklemotion/nokogiri  # HTML, XML, SAX, and Reader parser.

gem 'omniauth'  # https://github.com/omniauth/omniauth
gem 'omniauth-openid'  # https://github.com/omniauth/omniauth-openid
gem 'openid-redis-store'
gem 'omniauth-facebook'
gem 'omniauth-twitter'
gem 'omniauth-instagram'
gem 'omniauth-github'

gem 'omniauth-oauth2', require: false

gem 'omniauth-google-oauth2'
gem 'oj'  # https://github.com/ohler55/oj  # A fast JSON parser and Object marshaller as a Ruby gem.  # 又是弄 JSON 的
gem 'pg', '~> 0.21.0'  # PostgreSQL
gem 'pry-rails', require: false  # https://github.com/rweng/pry-rails  
# http://pryrepl.org/
# Pry is a powerful alternative to the standard IRB shell for Ruby.

gem 'r2', '~> 0.2.5', require: false  #  https://rubygems.org/gems/r2/versions/0.2.5
# https://github.com/mzsanford/R2rb/
# Library for swapping CSS values for right-to-left display
# 处理 CSS 的，方便左右布局切换，从左到右，从右到左的语言，方便切换

gem 'rake' # https://github.com/ruby/rake

gem 'thor', require: false  # https://github.com/erikhuda/thor
gem 'rinku'
gem 'sanitize'
gem 'sidekiq'

# for sidekiq web
gem 'tilt', require: false

gem 'execjs', require: false
gem 'mini_racer'
gem 'highline', require: false
gem 'rack-protection' # security

# Gems used only for assets and not required in production environments by default.
# Allow everywhere for now cause we are allowing asset debugging in production
group :assets do
  gem 'uglifier'
  gem 'rtlit', require: false # for css rtling
end

group :test do
  gem 'webmock', require: false
  gem 'fakeweb', '~> 1.3.0', require: false
  gem 'minitest', require: false
end

group :test, :development do
  gem 'rspec'
  gem 'mock_redis'
  gem 'listen', require: false
  gem 'certified', require: false
  # later appears to break Fabricate(:topic, category: category)
  gem 'fabrication', '2.9.8', require: false
  gem 'mocha', require: false
  gem 'rb-fsevent', require: RUBY_PLATFORM =~ /darwin/i ? 'rb-fsevent' : false
  gem 'rb-inotify', '~> 0.9', require: RUBY_PLATFORM =~ /linux/i ? 'rb-inotify' : false
  gem 'rspec-rails', require: false
  gem 'shoulda', require: false
  gem 'rspec-html-matchers'
  gem 'pry-nav'
  gem 'byebug', require: ENV['RM_INFO'].nil?
  gem 'rubocop', require: false
end

group :development do
  gem 'ruby-prof', require: false
  gem 'bullet', require: !!ENV['BULLET']
  gem 'better_errors'
  gem 'binding_of_caller'
  gem 'annotate'
  gem 'foreman', require: false
end

# this is an optional gem, it provides a high performance replacement
# to String#blank? a method that is called quite frequently in current
# ActiveRecord, this may change in the future
gem 'fast_blank', platform: :mri

# this provides a very efficient lru cache
gem 'lru_redux'

gem 'htmlentities', require: false

# IMPORTANT: mini profiler monkey patches, so it better be required last
#  If you want to amend mini profiler to do the monkey patches in the railties
#  we are open to it. by deferring require to the initializer we can configure discourse installs without it

gem 'flamegraph', require: false
gem 'rack-mini-profiler', require: false

gem 'unicorn', require: false, platform: :mri
gem 'puma', require: false
gem 'rbtrace', require: false, platform: :mri
gem 'gc_tracer', require: false, platform: :mri

# required for feed importing and embedding
gem 'ruby-readability', require: false

gem 'stackprof', require: false, platform: :mri
gem 'memory_profiler', require: false, platform: :mri

gem 'cppjieba_rb', require: false

gem 'lograge', require: false
gem 'logstash-event', require: false
gem 'logstash-logger', require: false
gem 'logster'

gem 'sassc', require: false

gem 'rotp'
gem 'rqrcode'

gem 'sshkey', require: false

if ENV["IMPORT"] == "1"
  gem 'mysql2'
  gem 'redcarpet'
  gem 'sqlite3', '~> 1.3.13'
  gem 'ruby-bbcode-to-md', github: 'nlalonde/ruby-bbcode-to-md'
  gem 'reverse_markdown'
end

gem 'webpush', require: false
