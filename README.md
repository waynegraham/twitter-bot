# THATCampVA Twitter Bot

# Setup

1. Install [Node.js](http://nodejs.org)
1. Create an account for the bot on [Twitter](http://www.twitter.com)
1. Register an application with the [Twitter
   API](https://dev.twitter.com)
1. Create an access token
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
node hello
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
to your project's `node_modules/twit/examples` directory:

```shell
$ cd node_modules/twit/examples
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
