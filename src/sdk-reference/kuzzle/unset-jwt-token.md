---
layout: side-code.html.hbs
language-tab:
  js: Javascript
  java: Android
  php: PHP
algolia: true
title: unsetJwtToken
---

# unsetJwtToken

```js
kuzzle.unsetJwtToken();
```

```java
kuzzle.unsetJwtToken();
```

```php
<?php
use \Kuzzle\Kuzzle;

$kuzzle = new Kuzzle('localhost');

$kuzzle->unsetJwtToken();
```

Unsets the internal JSON Web Token used for authentication, and stops all existing subscriptions.

---

## Return Value

Returns the `Kuzzle` SDK object to allow chaining.
