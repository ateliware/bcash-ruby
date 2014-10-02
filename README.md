#Bcash Ruby

[![Gem
Version](http://img.shields.io/gem/v/bcash-ruby.svg)](https://rubygems.org/gems/bcash-ruby)
[![Build Status](https://travis-ci.org/minestore/bcash-ruby.svg?branch=master)](https://travis-ci.org/minestore/bcash-ruby)
[![Code Climate](https://codeclimate.com/github/minestore/bcash-ruby/badges/gpa.svg)](https://codeclimate.com/github/minestore/bcash-ruby)
[![Coverage
Status](https://coveralls.io/repos/minestore/bcash-ruby/badge.png)](https://coveralls.io/r/minestore/bcash-ruby)

Ruby wrapper for the Bcash API. This gem provides wrapper for account and
transaction methods.

## Installation
    gem install bcash-ruby

## Resources
* [View Source on GitHub][code]
* [Report Issues on GitHub][issues]
* [Read More at the Wiki][wiki]

[code]: https://github.com/minestore/bcash-ruby
[issues]: https://github.com/minestore/bcash-ruby/issues
[wiki]: https://wiki.github.com/minestore/bcash-ruby

## Configuration

```ruby
Bcash.configure do |b|
  b.email = Rails.application.secrets.bcash["email"]
  b.token = Rails.application.secrets.bcash["token"]
end
```

## Usage Examples

### Verify Bcash return

```ruby
  data = {
    transacao: '2833',
    status: 'Transação em Andamento',
    cod_status: '0',
    valor_original: '2145.23',
    valor_loja: '2083.23',
    token:  '1211CF51917E074BC3784592C71FC'
  }

  client = Bcash::Client.new
  response = client.verify_return(data)
  response.verified? #true
```

## Supported Ruby Versions
This library aims to support and is [tested against][travis] the following Ruby
implementations:

* Ruby 1.9.3
* Ruby 2.0.0
* Ruby 2.1.0
* [Rubinius][]

[rubinius]: http://rubini.us/

If something doesn't work on one of these interpreters, it's a bug.

This library may inadvertently work (or seem to work) on other Ruby
implementations, however support will only be provided for the versions listed
above.

If you would like this library to support another Ruby version, you may
volunteer to be a maintainer. Being a maintainer entails making sure all tests
run and pass on that implementation. When something breaks on your
implementation, you will be responsible for providing patches in a timely
fashion. If critical issues for a particular implementation exist at the time
of a major release, support for that Ruby version may be dropped.

## License
Copyright (c) 2014 Raphael Costa and minestore, Inc. See [LICENSE][] for
details.

[license]: LICENSE
