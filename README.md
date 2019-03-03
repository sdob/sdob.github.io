# About me

I go in there and do things with computers.

# Things I've worked on

## Masqt

I'm a co-founder, thing-stacker, and dogfooder-in-chief at
[Masqt](https://masqt.com), a security-first approach to privacy and identity
management.

Architecturally, Masqt was designed
to scale fast and sideways, which means that the
email-processing back-end is made up of a fleet of
slightly unruly AWS Lambda functions, implemented variously
in Python and Node (depending on what makes the most sense; async
is free at point of use in JavaScript, which we exploit).

We used to
publish our source code under the MIT license until we were
persuaded against it.

## Defibs.ie

I'm the software lead on [defibs.ie](https://defibs.ie), where
we're (gradually) creating a community-built map of publicly-available
automated external defibrillators in Ireland.
Submissions of defib locations are [welcome](https://defibs.ie/submit).

The [codebase](https://github.com/defibs-ie)
comprises a React front-end talking
to a Django API.
We use map data from [mapbox.com](https://www.mapbox.com/)
and directions data from the
[Google Maps Directions API](https://developers.google.com/maps/documentation/directions/).
I'm not sold on the bundle size that you get with Uber's
[`react-map-gl`](https://uber.github.io/react-map-gl/),
however, so this may all change in the future.

## Fallen London

In 2018 I spent several months working, from alpha to launch,
on a re-design of the browser game [Fallen London](https://fallenlondon.com).
I did quite a lot of interesting things while I was working on
it, but that's not important here (and none of the source is
available anyway). I got the gig because I play it and
had contributed a few
moderately useful and popular browser extensions to fill in
gaps in the user interface. Some of these were made obsolete
by the re-design and some are still waiting to be updated to work
on the new site.

* [Fallen London Conversion Helper](https://github.com/sdob/fl-conversion-helper)
is the most popular and most ambitious extension I've created.
It has [its own page](https://gallmarch.github.io/fl-conversion-helper),
which describes its functionality from a gameplay perspective.
It's available on the
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-conversion/bajlcoahedhgjfpfgahdfaoeohmjbhfb)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fl-conversion-helper/).

  Technically speaking, it's a React/Redux app that sits on top of
an existing React/Redux app, using
[`mutation-summary`](https://github.com/rafaelw/mutation-summary)
to watch DOM elements and update the store.
This allows for a pretty clean layer of abstraction
between the DOM-manipulation code
and the pure-function stuff; it's an architectural decision
that's worked well for writing stateful web extensions that interact with
existing DOMs, and one I'd recommend.

* I took over responsibility for [Fallen London Goat Farmer](https://github.com/gallmarch/fl-goat-farmer),
originally written by another player. This works very similarly to Conversion Helper.

* [Fallen London Social Notifications](https://github.com/sdob/fl-social-notifications)
periodically pings the Fallen London servers for new messages for other players,
bringing irksome notification badges to the world of Fallen London.
It was about as complex an extension as I'm happy to write without
some proper state management (which is to say, not very complex at all),
but it did what it does sufficiently well that I was reluctant to touch the code.
Needs a rewrite to work on the new site.
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-social-noti/baebnomhiokfcpfadkjpkeoohmogecdb)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fl-conversion-helper/).

* [Fallen London Library](https://github.com/gallmarch/fl-library)
was written as a lark in response to a message in one of the 'feature wishlist'
threads that occasionally pop up on the [Fallen London subreddit](https://reddit.com/r/fallenlondon).
It took longer to publish the extension than it did to write it
and so inevitably it ended up more popular than code I've sweated bullets over.
Also needs rewriting.
[Chrome Web Store](https://chrome.google.com/webstore/detail/fallen-london-library/dodefappijdnbfcgmkbpenopdnnhmnki)
and
[addons.mozilla.org](https://addons.mozilla.org/en-US/firefox/addon/fallen-london-library/).


* [Fallen London Item Search](https://github.com/sdob/fl-search), the first extension, basically applies
display filtering to DOM elements based on text matches. It was written to scratch an itch, and
as is the way with such things, merely encouraged further scratching. Some of the architectural
decisions made sense in 2017, which was after all a very long time ago.
This was made obsolete when I got hired to work on the new site and folded in searching
to the UI.
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
