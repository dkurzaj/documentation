---
layout: side-code.html.hbs
language-tab:
  js: Javascript
  java: Android
  php: PHP
algolia: true
title: zrank
---

# zrank

```js
// Using callbacks (NodeJS or Web Browser)
kuzzle.memoryStorage.zrank('key', 'foo', function (err, position) {
  // callback called once the action has completed
});

// Using promises (NodeJS only)
kuzzle.memoryStorage.zrankPromise('key', 'foo')
  .then(position => {
    // resolved once the action has completed
  });
```

```java
kuzzle.memoryStorage.zrank("key", "member", new ResponseListener<Long>() {
  @Override
  public void onSuccess(int position) {
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
  $position = $kuzzle->memoryStorage()->zrank('key', 'foo');
}
catch (ErrorException $e) {

}
```

> Callback response:

```json
0
```

Returns the position of an element in a sorted set, with scores in ascending order. The index returned is 0-based (the lowest score member has an index of 0).

[[_Redis documentation_]](https://redis.io/commands/zrank)

---

## zrank(key, member, [options], callback)

| Arguments | Type | Description |
|---------------|---------|----------------------------------------|
| `key` | string | Key identifier |
| `member` | string | Member of the sorted set |
| `options` | JSON Object | Optional parameters |
| `callback` | function | Callback |

---

## Options

| Option | Type | Description | Default |
|---------------|---------|----------------------------------------|---------|
| `queuable` | boolean | Make this request queuable or not  | `true` |


---

## Callback Response

Returns an integer containing the member's position in the sorted set.
