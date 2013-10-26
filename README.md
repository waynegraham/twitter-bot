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


