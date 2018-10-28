# webdriverio-simple-chromedriver-setup

An example of a very simple WebdriverIO setup with chromedriver - no Java dependencies.

## Run demo test

```
$ npm i
$ npm test
```

## How did you make this?

- npm init -y
- npm i webdriverio chromedriver --dev
- ./node_modules/.bin/wdio config
    - use all defaults except for the following:
        - reporter: spec
        - services: chromedriver
- change/add in `wdio.conf.js`:
    - `capabilities.browserName: 'firefox'` -> `capabilitites.browserName: 'chrome'`
    - `port: '9515'` - needed to tell webdriverio to use the same port that chromedriver uses
    - `path: '/'` - same as port
- download demo test:
    - mkdir -p test/specs
    - curl https://raw.githubusercontent.com/webdriverio/webdriverio/master/examples/wdio/mocha/mocha.test.js -o test/specs/demo.js
- change script in package.json: `"test": "wdio"`
