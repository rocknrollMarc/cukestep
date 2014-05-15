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

    mount Cukestep::Engine => "/cukestep", as: "cukestep"

### Start your Rails application and navigate to

    /cukestep/steps

### Pivotal Tracker

Inject `/assets/bookmarklet.js` in your browser to decorate the Pivotal Tracker story description field.

Note: Pivotal Tracker runs using SSL. In order to test locally, run Charles, map https->http, configure SSL proxying and visit the endpoint URL in the browser to accept the SSL certification restriction.

### Example

![Pivotal Tracker CUkestep Example](http://cl.ly/image/1h0K0X2x2126/pivotal_tracker_cukestep_example.png)

## Contributing

1. Fork it ( https://github.com/[my-github-username]/cukestep/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
