# generator-sub 
[![Build Status](https://secure.travis-ci.org/doug-wade/generator-sub.svg?branch=master)](https://travis-ci.org/doug-wade/generator-sub)[![dependencies](https://david-dm.org/doug-wade/generator-sub.svg)](https://david-dm.org/doug-wade/generator-sub)[![npm version](https://badge.fury.io/js/generator-sub.svg)](https://badge.fury.io/js/generator-sub)

> A Yeoman generator for writing cli apps inspired by 37signals sub

## Features

#### For your users

* Updating from git and npm
* User-managed config
* Help parsed from subcommand comments

#### For you

* Eslint

## Installation

First, install [Yeoman](http://yeoman.io) and generator-sub using [npm](https://www.npmjs.com/) (we assume you have pre-installed [node.js](https://nodejs.org/)).

```bash
npm install -g yo
npm install -g generator-sub
```

Then generate your new project:

```bash
yo sub
```


## Running the generated cli app locally

For example, suppose you generated a cli app called sub.

First, link the new package

```bash
npm link
```
Then, get the help

```bash
» sub help
A simple cli application. Broken into sub commands, invoked under sub:
    example  an example command.  Ex. sub example
    help    (also: -h or --help) print this help message.  Ex. sub help
```

And run the example sub command

```bash
» sub example
You ran the example command!
```


## Adding a new sub command

Say you wanted to add a new subcommand, random, which prints a random number between 0 and a provided argument when invoked.  First, generate a new sub command

```bash
yo sub:command
```

And verify that everything worked as anticipated

```bash
npm link
sub random
> You ran the random command!
```

Then, add your new logic inside the exported function inside lib/random.js

```javascript
/**
 * Returns a random number between 0 and the argument value
 * Usage:
 *      sub random 100
 *      > 80.6944249663502
 */
module.exports = function(argv){
  console.log(Math.random()*(+argv._[1]));
}
```

And then test your new command locally

```bash
sub random 100
> 80.6944249663502
```


## Example

See a sample cli app generated using this generator [here](https://github.com/prekolna/dnd-roller).


## Inspired By

This generator is Inspired [37signals sub](https://github.com/basecamp/sub).  Read more about [their pattern](http://37signals.com/svn/posts/3264-automating-with-convention-introducing-sub).


## Getting To Know Yeoman

Yeoman has a heart of gold. He&#39;s a person with feelings and opinions, but he&#39;s very easy to work with. If you think he&#39;s too opinionated, he can be easily convinced. Feel free to [learn more about him](http://yeoman.io/).


## Contributing

Please make sure it passes eslint.

    eslint .

There are also tests, but they do not pass `¯\_(ツ)_/¯`.

    npm test

Send me a pull request!  You can put your name in the credits here if you're into that sort of thing.


## TODO

1. Make the tests pass
1. Add auto-updating on a schedule
1. sub generator for sub command

## License

MIT © [Doug Wade](dougwade.io)

# Support
[![Support via Gratipay](https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.svg)](https://gratipay.com/~doug-wade/)
