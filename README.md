# superagent-rxjs
[![Build Status](https://travis-ci.org/mrtnbroder/superagent-rxjs.svg?branch=master)](https://travis-ci.org/mrtnbroder/superagent-rxjs)
[![Coverage Status](https://coveralls.io/repos/github/mrtnbroder/superagent-rxjs/badge.svg?branch=master)](https://coveralls.io/github/mrtnbroder/superagent-rxjs?branch=master)
[![Dependency Status](https://dependencyci.com/github/mrtnbroder/superagent-rxjs/badge)](https://dependencyci.com/github/mrtnbroder/superagent-rxjs)

Return an RxJS v5 Observable from your superagent request

## Installation

Add it to your project via npm:

```shell
npm i -S superagent-rxjs
```

if you haven't already, also add superagent as a dependency to your project:

```shell
npm i -S superagent
```

## Usage

```js
import superagent from 'superagent'
import observify from 'superagent-rxjs'

// adds the .observify() method to the superagent Request prototype
const request = observify(superagent)

// use it!
const observable = request.get('http://example.com').observify()
const subscription = observable.subscribe()

// calling unsubscribe before the request has finished will abort the request
subscription.unsubscribe()
```

## API

### [`observify :: Request -> Request`](https://github.com/mrtnbroder/superagent-rxjs/blob/master/src/index.js#L4-L29)

Adds the `observify` method to superagent's `Request.prototype` and returns a new superagent
