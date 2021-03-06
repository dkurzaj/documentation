---
layout: side-code.html.hbs
algolia: true
language-tab:
  js: HTTP
  json: Other protocols
title: mDelete
---

# mDelete

{{{since "1.0.0"}}}

<blockquote class="js">
<p>
**URL:** `http://kuzzle:7512/_mDelete`  
**Method:** `DELETE`  
**Body:**
</p>
</blockquote>



```js
indexes: [
  "index1",
  "index2",
  ...
}
```


<blockquote class="json">
<p>
**Query**
</p>
</blockquote>


```json
{
  "controller": "index",
  "action": "mDelete",
  "body": {
    "indexes": [
      "index1",
      "index2"
    ]
  }
}
```

>**Response**

```javascript
{
  "status": 200,
  "error": null,
  "action": "mDelete",
  "controller": "index",
  "requestId": "<unique request identifier>",
  "result": { // list of actual deleted indexes
    "deleted":[
      "index1",
      "index2"
    ]
  }
}
```

Deletes a set of `indexes` specified in the body. The current user must have permission to delete the indexes.

If no `indexes` is specified in the body, all the indexes that the current user is allowed to delete will be deleted.

That means: if Kuzzle contains indexes "index1", "index2" and "index3",
but current user is only allowed to delete "index1" and "index2", only both of those are deleted,
and "index3" is kept in the persistent storage layer.

The response contains the list of indexes that were actually deleted.
