# CamperVan, a Campfire to IRC bridge

## Features

CamperVan, as far as your IRC client is concerned, is just another ircd.

Campfire rooms and users are mapped as IRC channels and nicks. Campfire
messages, even custom ones such as tweets and sounds, are translated
for an IRC client to understand.

## Mappings

Wherever possible, Campfire messages and IRC commands are translated
bidirectionally. Some of the mappings are:

    IRC                         Campfire
    ---                         --------
    #day_job                    "Day Job" room
    joe_bob (nick)              Joe Bob (user)
    @admin_user (nick)          An admin user
    "joe_bob: hello" (message)  "Joe Bob: hello" (message)
    https://tweet_url           Tweet message
    /me waves                   *waves*

    /LIST                       List rooms
    /JOIN #day_job              Join the "Day Job" room
    /PART #day_job              Leave the "Day Job" room
    /WHO #day_job               List users in "Day Job"

    /MODE +i #day_job           Lock room
    /MODE -i #day_job           Unlock room

    /TOPIC #day_job new topic   Change room's topic to "new topic"

## Usage

### Installation

    gem install camper_van
    camper_van --help

### Running CamperVan

    camper_van

Then, from your IRC client, set up a connection to `localhost:6667`. To
authenticate with Campfire, you must configure your connection's
password (the IRC PASS command) to be

    campfire_subdomain:api_key

Connect, and `/LIST` will show you the irc channels / campfire rooms you
have access to.

## Development

CamperVan uses:

* ruby 1.9.2 + minitest
* [bundler](http://gembundler.com/)
* [eventmachine](http://rubyeventmachine.com/)
* [firering](https://github.com/EmmanuelOga/firering)
* [logging](https://github.com/TwP/logging)
* [trollop](http://trollop.rubyforge.org/)

## License

See LICENSE for details.

## Contributing

Fork, patch, test, pull request.

