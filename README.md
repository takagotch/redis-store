### redis-store
---
https://github.com/redis-store/redis-store

```
brew install redis
git clone git://github.com/redis-store/redis-store.git
cd redis-store
bundle install
bundle exec rake

s.add_dependency 'redis-store', '>= 1.4', '< 2'

```

```ruby
config.gem "redis-store", :lib => "redis-store"
require "redis-store"
config.cache_store = :redis_store, "redis://192.168.1.132:6380/12"

config.cache_store = :redis_store, { :host => "localhost",
                                     :port => 6379,
                                     :db => 0,
                                     :password => "ntsecret",
                                     :namespace => "cache",
                                     :expires_in => 90.minutes }

config.gem "reids-store"
My::Application.config.session_store :redis_store, :servers => "redis://:secret@127.0.0.1:6999/10"
#Instead of :servers => "" you can also use a hash, e.g. :servers => { :host => "localhost", :port => 6380, :db => 0, :namespace => 'session' }
:expire_in => # TTL in seconds - :expires_in and :expire_after work as well

use Rack::Session::Redis, :redis_server => "redis://secret@127.0.0.1:6999/10"

```

```
```
