---
layout: side-code.html.hbs
language-tab:
  js: Javascript
  java: Android
  php: PHP
algolia: true
title: keys
---

# keys

```js
// Using callbacks (NodeJS or Web Browser)
kuzzle.memoryStorage.keys('foo*', function (err, keys) {
  // callback called once the action has completed
});

// Using promises (NodeJS only)
kuzzle.memoryStorage.keysPromise('foo*')
  .then(keys => {
    // resolved once the action has completed
  });
```

```java
kuzzle.memoryStorage.keys("foo*", new ResponseListener<String[]>() {
  @Override
  public void onSuccess(String[] keys) {
    // callback called once the action has completed
  }

  @Override
  public void onError(JSONObject error) {
  }
});
```

```php
<?php

use \Kuzzle\Kuzzle;


$kuzzle = new Kuzzle('localhost');

try {
  $keys = $kuzzle->memoryStorage()->keys('foo*');
}
catch (ErrorException $e) {

}
```

> Callback response:

```json
[
  "foo",
  "foobar",
  "foofighters"
]
```

Returns all keys matching the provided pattern.

[[_Redis documentation_]](https://redis.io/commands/keys)

---

## keys(pattern, [options], callback)

| Arguments | Type | Description |
|---------------|---------|----------------------------------------|
| `pattern` | string | Pattern used to filter the returned key names |
| `options` | JSON Object | Optional parameters |
| `callback` | function | Callback |

---

## Options

| Option | Type | Description | Default |
|---------------|---------|----------------------------------------|---------|
| `queuable` | boolean | Make this request queuable or not  | `true` |

---

## Callback Response

Returns an array of key names matching the provided pattern.
