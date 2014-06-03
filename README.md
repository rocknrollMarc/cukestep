# Cukestep

Cukestep exposes your system's Gherkin steps to the outside world through a Rails Engine.

## Installation

Add this line to your application's Gemfile:

    gem 'cukestep'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install cukestep

## Usage

### Mount the engine

    # routes.rb
    mount Cukestep::Engine => "/cukestep", as: "cukestep"

### Start your Rails application and navigate to

    /cukestep/steps

At this point - you should be seeing a JSON output of your Gherkin steps.

### Configuration

*Rails*

To exclude a support file from the autoload path, create an initializer class and redefine `excluded_code_file_paths`.

```ruby
# #{Rails.root}/config/initializers/cukestep_config.rb
class CukestepConfig < Cukestep::Configuration
  def excluded_code_file_paths
    ['features/support/extranet.rb']
  end
end

Cukestep.config = CukestepConfig.new
```

*Browser*

Modify `Cukestep.url =` within [example/assets/bookmarklet.js](https://github.com/adriancb/cukestep/blob/master/example/assets/bookmarklet.js) and change the URL to point to your local development environment. For production, modify the URL to point to your production server.

*Note:* Pivotal Tracker and Trello run on SSL. In order to test locally, run [Charles Proxy](http://www.charlesproxy.com/), map https->http, configure SSL proxying and visit the endpoint URL in the browser to accept the SSL certification restriction.

### Pivotal Tracker and Trello

Inject [example/assets/bookmarklet.js](https://github.com/adriancb/cukestep/blob/master/example/assets/bookmarklet.js) in your browser as a bookmarklet to decorate the Pivotal Tracker story/Trello description field.

### Examples - Pivotal Tracker and Trello

![Pivotal Tracker Cukestep Example](http://cl.ly/Vox0/pivotal_tracker_cukestep_example.png.png)

![Trello Cukestep Example](http://cl.ly/VpE7/trello_cukestep_example.png.png)

### Shoutouts

Cukestep makes heavy use of [At.js](https://github.com/ichord/At.js).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/cukestep/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
