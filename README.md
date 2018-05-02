# ResoWebApi

A Ruby library to connects to MLS servers conforming to the [RESO Web API][reso-web-api] standard.

[reso-web-api]: https://www.reso.org/reso-web-api/

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'reso_web_api'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install reso_web_api

## Usage

Basic

```ruby
require 'reso_web_api'

ResoWebApi.configure do |config|
  config.service_url = 'https://api.my-mls.org/RESO/OData/'
  config.auth_url    = 'https://oauth.my-mls.org/connect/token'
  config.auth_scope  = 'odata'
  config.api_key     = 'deadbeef'
  config.api_secret  = 'T0pS3cr3t'
end

# Iterate over all properties -- WARNING! Might take a long time
ResoWebApi.client.properties.each do |property|
  puts "#{property['ListPrice']} #{property['StandardStatus']}"
end
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/wrstudios/reso_web_api.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).