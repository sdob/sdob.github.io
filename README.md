This is just a brief walkthrough of the more notable
repos under [https://github.com/sdob](https://github.com/sdob).

## Masqt

I'm a co-founder, thing-stacker, and dogfooder-in-chief at
[Masqt](https://masqt.com), a security-first approach to privacy and identity
management.  It's largely undocumented,
in heavy alpha, and undergoing rapid development, but you're
welcome to take a look.  We're at least moderately less likely to surrender
your email address to hackers than most startups.

Architecturally, Masqt is designed
to scale fast and sideways, which means that the
email-processing back-end is made up of a fleet of
slightly unruly AWS Lambda functions, implemented variously
in Python and Node (depending on what makes the most sense; async
is free at point of use in JavaScript, which we exploit).
Beware that the repos contain high levels of
[founder code](https://www.onebigfluke.com/2015/04/what-is-founder-code.html).

* [`balveda`](https://github.com/masqt/balveda)
is our web front-end: a moderately complex React/Redux
application that handles registration and user preferences.

* [`grey-area`](https://github.com/masqt/grey-area)
is the web-facing API (implemented, like most of our backend, in Django).
It receives the most traffic and the largest
number of intrusion attempts, so it gets the
most love (and dedicated servers).

* [`amorphia`](https://github.com/masqt/amorphia)
and [`sleeper-service`](https://github.com/masqt/sleeper-service)
are the first point of contact for incoming email for Masqt users.
We use `amorphia` to split up recipients
and pass them to `sleeper-service`, which runs the processing
asynchronously.

* [`attitude-adjuster`](https://github.com/masqt/attitude-adjuster)
is our blocking service, which is responsible for generating and handling the
links we create to let our users block unwanted or abusive content.

* [`ethics-gradient`](https://github.com/masqt/ethics-gradient)
manages users' bandwidth quotas (we operate soft and hard caps for
free-tier users).

* [`sensia`](https://github.com/masqt/sensia)
and [`samwaf`](https://github.com/masqt/samwaf)
(experimental) are being built to handle replies
to Masqt emails (an upcoming premium-tier feature).

We've also published to NPM our React 16-compatible forks of two projects
that are important to `balveda`:

* [`@masqt/riek`](https://www.npmjs.com/package/@masqt/riek)
([repo](https://github.com/masqt/riek))
is a fork of [`riek`](https://www.npmjs.com/package/riek),
an assortment of editable-in-place React form components.

* [`@masqt/react-highlight`](https://www.npmjs.com/package/react-highlight)
([repo](https://github.com/masqt/react-highlight))
forks [`react-highlight`](https://www.npmjs.com/package/react-highlight),
a `riek` dependency.

## Defibs.ie

I'm the software lead on [defibs.ie](https://defibs.ie), where
we're (gradually) creating a community-built map of publicly-available
automated external defibrillators in Ireland.
Submissions of defib locations are [welcome](https://defibs.ie/submit).

The [codebase](https://github.com/defibs-ie)
comprises a React front-end talking
to a Django API.
We're using map data from [mapbox.com](https://www.mapbox.com/)
and directions data from the
[Google Maps Directions API](https://developers.google.com/maps/documentation/directions/).
I'm not sold on the bundle size that you get with Uber's
[`react-map-gl`](https://uber.github.io/react-map-gl/),
however, so this may all change in the future.

## Fallen London

I play [Fallen London](http://fallenlondon.com), which takes place (according
to its publishers) in 'a dark and hilarious Gothic underworld where all your
actions have consequences' and consequently is a natural fit for
academics of all stripes. I've contributed a few thoroughly
unofficial helpful browser extensions, which have achieved
a modest popularity among the player-base:

* [Fallen London Conversion Helper](https://github.com/sdob/fl-conversion-helper)
is the most popular and most ambitious extension I've created.
It has [its own page](https://gallmarch.github.io/fl-conversion-helper),
which describes its functionality from a gameplay perspective.
It's available on the
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-conversion/bajlcoahedhgjfpfgahdfaoeohmjbhfb)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fl-conversion-helper/).

  Technically speaking, it's a React/Redux app that sits on top of
an existing jQuery-and-DHTML page, using
[`mutation-summary`](https://github.com/rafaelw/mutation-summary)
to watch DOM elements and update the store.
This allows for a pretty clean layer of abstraction
between the DOM-manipulation code
and the pure-function stuff; it's an architectural decision
that's worked well for writing stateful web extensions that interact with
existing DOMs, and one I'd recommend.

* [Fallen London Social Notifications](https://github.com/sdob/fl-social-notifications)
periodically pings the Fallen London servers for new messages for other players,
bringing irksome notification badges to the world of Fallen London.
It's about as complex an extension as I'm happy to write without
some proper state management (which is to say, not very complex at all),
but it does what it does sufficiently well that I'm reluctant to touch the code.
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-social-noti/baebnomhiokfcpfadkjpkeoohmogecdb)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fl-conversion-helper/).

* [Fallen London Library](https://github.com/gallmarch/fl-library)
was written as a lark in response to a message in one of the 'feature wishlist'
threads that occasionally pop up on the [Fallen London subreddit](https://reddit.com/r/fallenlondon).
It took longer to publish the extension than it did to write it
and so inevitably it ended up more popular than code I've sweated bullets over.
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-library/dodefappijdnbfcgmkbpenopdnnhmnki)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fallen-london-library/).


* [Fallen London Item Search](https://github.com/sdob/fl-search), the first extension, basically applies
display filtering to DOM elements based on text matches. It was written to scratch an itch, and
as is the way with such things, merely encouraged further scratching. Some of the architectural
decisions made sense in 2017, which was after all a very long time ago.
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-item-search/jmldnifgockhcidgdinhbfciiphkamkl)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fallen-london-item-search1/).



## Daire Ipsum

[Lorem Ipsum](https://daire-ipsum.herokuapp.com) for scuba-diving physicists from Kerry.
Created in part ([repo](https://github.com/sdob/daire-ipsum)) as a way to teach
myself server-side Node when it was the new hotness, but
primarily to annoy a very good friend.

It was at best moderately successful at either, but
the API is the stablest software I've ever written.
