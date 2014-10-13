# THATCampVA Twitter Bot

This is a brief workshop that spun out of the [Bots](http://virginia2013.thatcamp.org/2013/10/10/bots/)
at [THATCamp Virginia](http://virginia2013.thatcamp.org/).


# tl;dr

1. Install [Node.js](http://nodejs.org)
1. Create an account for the bot on [Twitter](http://www.twitter.com)
1. Register an application with the [Twitter
   API](https://dev.twitter.com)
1. Be sure to set the permissions to read/write
1. Create an access token (if you created the token **before** you set the
   application to be read/write, you will need to regenerate the token)
1. Install the [twit node module](https://github.com/ttezel/twit)
1. Configure your bot with the `consumer key`, `consumer secret`,
   `access token`, and `access token secret`
1. Unleash your bot to wreak havok upon an unsuspecting public

## node.js

To test to make sure everything is working properly, create a file named
`hello.js` and edit it with your favorite text editor to read like this:

```javascript
console.log("Welcome to THATCampVA!");
```

Save it, and run this command in the terminal to execute the program:

```shell
$ node hello
```

You should see the console print `Welcome to THATCampVA!`; if you
didn't, something went horribly wrong.

## Twitter Account
This is a bot, so be careful that you're not spamming people and
therefor feel the wrath of Twitter and getting banned. For this reason,
it's a good idea to creeate an account on Twitter, just in case there is
some faulty bot logic along the way.

## Twitter API
Twitter gives developers the ability to register applications to
programatically interact with their platform. Once you've created an
application, take a look at the OAuth settings and note your *consumer
key* and *consumer secret* (you'll need these).

After you have this, create an *access token* (it takes a few minutes
for this to propogate Twitter's system, so be patient).

## Project Setup

To speed things along, I set up a repository with a file to tell node's
package manager ([npm](https://npmjs.org/)) what this application needs.
You will need to clone the repository, then tell node to resolve the
dependencies:

```console
$ git clone https://github.com/waynegraham/twitter-bot.git
$ cd twitter-bot
$ npm install
```
I'll note that I have a few other things included, mostly development
dependencies that I use as boilerplate for new projects using [Grunt](http://gruntjs.com/)
that helps automate a lot of the things I do in development.

## The Bot
The [Twit](https://github.com/ttezel/twit) module actually ships with a
bot, so getting up and going is really simple. In the console, change in
to your project's `node_modules/twit` directory:

```shell
$ cd node_modules/twit
```

In that directory, we need to create a file named `config1.js` with the
credentials we generated on Twitter.

```javascript
module.exports = {
  consumer_key: "...",
  consumer_secret: "...",
  access_token: "...",
  access_token_secret: "..."
}
```

**Note:** Documentation for this is in the `twit` module's `README.md`
file.

You can now fire up the twitter bot with the following command (assuming
you're in the examples directory):

```shell
$ node examples/rtd2.js
```
You're now running a Twitter bot! The bot will execute every 40 seconds
(the 40000 on the last line). If you want this to execute faster, set
this number lower (like 10000, or 10 seconds).

## What's Going On?
This program doesn't do much. Every 40 seconds it attempts to do one of
three things:

1. Tweet a random popular tweet from github
1. Follow a friend of one of your followers
1. Unfollow someone who hasn't followed you back.

# Twitter Considerations
Twitter doesn't ban bots, but it does what it can to prevent spam. This
is a bit of a balancing act when you're writing a bot. You just need to
be careful not to show the behavior indicative of a spam bot.

## Twitter's Rules
Right now the bot does one of three things: retweets, follows, and
unfollows. If you set the refresh interval too low (like lowering to
every 10 seconds), you might have your account suspended and get a note
from Twitter that your practicing "aggressive following." There's not an
actual stated limit, so Twitter has some latitude to enforce the limit
as they see fit (as with their entire list of rules).

## Twitter's API

[Twitter's API](https://dev.twitter.com/docs/api/1.1) at the 1.1 stage
is reasonablys stable, and notes all of the actions you can program. If
you want to do something with the API, it's worth reading through the
documentation to see what's possible.

# Heroku

Right now the bot will run on your local computer when you have it
running. If you want this to run on a server, [Heroku](http://heroku.com)
provides a nice hosting service for this kind of thing.

To run on heroku, you will need to create a file named `Procfile` tell
tell the service what to run. Create a file with the following in it:

```
web: node twitter-bot.js
```

## TODO: finish deploying to heroku



# node.js

Here are some resources for leveling up your node skills:

* [The Node Beginner Book](http://www.nodebeginner.org/)
* [Eloquent JavaScript](http://eloquentjavascript.net/)
* [Node.js for Beginners](http://net.tutsplus.com/tutorials/javascript-ajax/node-js-for-beginners/)
* [How to Node](http://howtonode.org/)
* [Node Guide](http://nodeguide.com/)
* [Node.js Tutorials at Project 70](http://project70.com/)
* [Masting node.js](http://visionmedia.github.io/masteringnode/)
* [Nodetuts](http://nodetuts.com/)
* [nodecasts](http://nodecasts.net/)
