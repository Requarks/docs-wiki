# Storage

### Base Class Example

```javascript
module.exports = {
  key: 'example',
  title: 'Example Storage',
  props: {
​
  },
  activated(opts) {
​
  },
  deactivated(opts) {
​
  },
  created(opts) {
​
  },
  updated(opts) {
​
  },
  deleted(opts) {
​
  },
  renamed(opts) {
​
  }
}
```

### Properties

* **key**: A short, unique and camelCase-formatted name for this module.
* **title**: The full name of the module.
* **props**: An object of user editable properties. See [Module Properties](properties.md) for more info.

### Events

