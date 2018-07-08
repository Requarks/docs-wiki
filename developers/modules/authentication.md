# Authentication

An authentication module adds new ways for users to login to the application. It consists of properties that can be set by the user as well as methods that are called on certain events \(e.g. during initialization\).

Authentication modules are located in `/server/modules/authentication`.

A unique folder is created for each module. The folder contains two files:

* **definition.yml**
* **authentication.js**

## definition.yml

```javascript
/* global WIKI */

// ------------------------------------
// Example Auth Account
// ------------------------------------

const ExampleStrategy = require('example')

module.exports = {
  key: 'example',
  title: 'Example Authentication',
  useForm: false,
  props: {

  },
  init (passport, conf) {
    passport.use('example',
      new ExampleStrategy({
        propA: conf.propA,
        propB: conf.propB
      }, function (accessToken, refreshToken, profile, cb) {
        WIKI.db.users.processProfile(profile).then((user) => {
          return cb(null, user) || true
        }).catch((err) => {
          return cb(err, null) || true
        })
      }
      ))
  }
}
```

### Properties

* **key**: A short, unique and camelCase-formatted name for this module.
* **title**: The full name of the module.
* **useForm**: Whether a user/email + password form should be displayed. _\(Should be_ `false` _for oauth2 based.\)_
* **props**: An object of user editable properties. See [Module Properties](properties.md) for more info.

### Events



