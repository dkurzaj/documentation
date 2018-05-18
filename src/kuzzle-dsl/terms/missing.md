---
layout: full.html.handlebars
algolia: true
title: missing
---

# missing

{{{since "1.0.0"}}}

A filter matching documents with a missing field.

## Example

Given the following documents:

```javascript
{
  firstName: 'Grace',
  lastName: 'Hopper',
  city: 'NYC',
  hobby: 'computer',
  alive: false
},
{
  firstName: 'Ada',
  lastName: 'Lovelace',
  city: 'London',
  hobby: 'computer',
}
```

The following filter validates the second document:

```javascript
{
  missing: {
    field: 'alive'
  }
}
```
