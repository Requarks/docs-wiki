# Logging

A logging module adds a new destination for logs to be sent to. All logging modules are based on Winston transport implementation, which is a popular logging library for Node.js.

Logging modules are located in `/server/modules/logging`.

A unique folder is created for each module. The folder contains two files:

* **definition.yml**
* **logger.js**

## definition.yml <a id="definition-yml"></a>

This file contains information about your module.

{% code-tabs %}
{% code-tabs-item title="definition.yml" %}
```yaml
key: example
title: Example Logger
description:  Some description for this logging module
author: John Doe
logo: https://static.requarks.io/logo/example.svg
website: https://requarks.io/
defaultLevel: warn
props:
  firstExampleProperty: String
  secondExampleProperty: Number
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Properties <a id="properties"></a>

* **key**: A short, unique and lowercase name for this module. It must match exactly the module folder name! _Do not use spaces or special characters._
* **title**: The full name of the module.
* **description**: A short description of the module.
* **author**: The name of the author of the module.
* **logo**: URL to the SVG logo for this module.
* **website**: URL to the logging service website / author of the module.
* **defaultLevel**: The minimum level for logging events \(default: `warn`\):
  * `error`
  * `warn`
  * `info`
  * `debug`
* **props**: An object of user editable properties. See [Module Properties](https://docs.requarks.io/wiki/v/2.x/developers/modules/properties) for more info.

## logger.js <a id="authentication-js"></a>

This file contains methods that will be called upon initialization.

{% code-tabs %}
{% code-tabs-item title="logger.js" %}
```javascript
const winston = require('winston')

// ------------------------------------
// Example Logger
// ------------------------------------

module.exports = {
  init (logger, conf) {
    require('example')
    logger.add(new winston.transports.Example({
      propA: conf.propA,
      propB: conf.propB
      level: conf.level
    }))
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

 All methods are required and must be implemented.

### init <a id="init"></a>

 Upon initialization of Wiki.js \(both startups or restarts\).

```javascript
init (logger, conf) { }
```

Parameter **logger** is the Winston instance on which your logging transport can be added.

Parameter **conf** is an object containing the configuration of the logging transport. For example, if you defined properties `clientId` and `clientSecret` for the module props, `conf` will be an object with properties `clientId` and `clientSecret` containing the values entered by the user in the administration area. It also contains the `level` parameter which is selected by the user and should be respected.

Learn more about Winston transports [here](https://github.com/winstonjs/winston#transports).

