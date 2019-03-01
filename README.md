Electracore
=======

[![Build Status](https://travis-ci.org/bitpay/bitcore.svg?branch=master)](https://travis-ci.org/bitpay/bitcore)
[![Coverage Status](https://img.shields.io/coveralls/bitpay/bitcore.svg)](https://coveralls.io/r/bitpay/bitcore)

A pure, powerful core for your Electra project.

Electracore is a complete, native interface to the Electra network, and provides the core functionality needed to develop
apps for Electra.

#Principles

Electra is a blockchain using the highly-secure and power efficient NIST5 algorithm. Combining temporary Proof-of-Work with high Proof-of-Stake, the Electra coin (ECA) is unique in its distribution. On June 16, 2017, Electra entered "Super Rewards Bonanza" stage for 24 hours (Blocks 11522-11810). During this time, 95% of the proof-of-work coins were mined. At block 11811, Electra swapped to Proof-of-Stake with an annual interest rate of 50% until block 112200. This created a gold-rush period, promoting the network (or was hoped to) and rapidly increasing the amount of ECA. The 30bil ECA is a soft limit, and will be controlled by the POS Block rewards.

**Electracore unchains developers from fallible, centralized APIs, and provides the tools to interact with the real Electra network.**

#Get Started

Electracore runs on [node](http://nodejs.org/), and can be installed via [npm](https://npmjs.org/):

```
npm install Electracore
```

It is a collection of objects useful to Litecoin applications; class-like idioms are enabled via[Soop](https://github.com/bitpay/soop).
In most cases, a developer will require the object's class directly. For instance:

```javascript
var Electracore = require('Electracore');
var Address = Electracore.Address;
var Transaction = Electracore.Transaction;
var PeerManager = Electracore.PeerManager;
```

#Examples

Examples are provided [here](examples.md)
Build the examples by installing and running gulp:

```
npm install -g gulp
gulp
```

Javascript files available at [/examples](/examples) folder.


#Security

Please use at your own risk.

Electracore is still under heavy development and not quite ready for "drop-in" production use. If you find a security issue,
please email  support@electraproject.org

#Contributing

Electracore needs some developer love. Please send pull requests for bug fixes, code optimization, and ideas for improvement.

#Browser support

## Building the browser bundle

To build Electracore full bundle for the browser (this is automatically executed after you run `npm install`):

```
node browser/build.js -a
```

This will generate a `browser/bundle.js` file which you can include in your HTML to use Electracore in the browser.

##Example browser usage

From example/simple.html

```html
<!DOCTYPE html>
<html>
  <body>
    <script src="../browser/bundle.js"></script>
    <script>
      var Electracore = require('Electracore');
      var Address = Electracore.Address;
      var a = new Address('sgrHPw4aEPos8YJDNfefsUSjPYWc5fzpLE');
      console.log('sgrHPw4aEPos8YJDNfefsUSjPYWc5fzpLE is valid? '+a.isValid());
    </script>
  </body>
</html>
```

You can check a more complex usage example at examples/example.html.

## Generating a customized browser bundle

To build the main Electracore bundle, run:

```
node browser/build.js -m
```

To build all features into the Electracore bundle (which will lead to a large file size), run:

```
node browser/build.js -a
```

To generate a customized Electracore bundle, you can specify which submodules you want to include in it with the -s option:

```
node browser/build.js -s Transaction,Address
```

This will generate a `browser/bundle.js` containing only the Transaction and Address class, with all their dependencies.
Use this option if you are not using the whole Electracore library, to optimize the bundle size, script loading time, and general resource usage.

## Tests

Run tests in node:

```
mocha
```

Or generate tests in the browser:

```
grunt shell
```

And then open test/index.html in your browser.

To run the code coverage report:

```
npm run-script coverage
```

And then open coverage/lcov-report/index.html in your browser.

#License

**Bitcore Code released under [the MIT license](https://github.com/bitpay/bitcore/blob/master/LICENSE).**

Copyright 2013-2014 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/bitpay/bitcore/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
