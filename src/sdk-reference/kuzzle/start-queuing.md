---
layout: side-code.html.hbs
language-tab:
  js: Javascript
  java: Android
  php: PHP
algolia: true
title: startQueuing
---

# startQueuing

```js
kuzzle.startQueuing();
```

```java
kuzzle.startQueuing();
```

```php
<?php

// not implemented (this SDK uses HTTP and is thus stateless)
```

Starts the requests queuing. Works only in offline mode, and if the [autoQueue]({{ site_base_path }}sdk-reference/kuzzle/#properties) option is set to `false`.

---

## Return Value

Returns the `Kuzzle` SDK object to allow chaining.
