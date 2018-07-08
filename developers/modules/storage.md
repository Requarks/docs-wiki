# Storage

### Base Class Example

```javascript
module.exports = {
  key: 'example',
  title: 'Example Storage',
  props: {
​
  },
  async activated (opts) {
​
  },
  async deactivated (opts) {
​
  },
  async init (opts) {
  
  },
  async created (opts) {
​
  },
  async updated (opts) {
​
  },
  async deleted (opts) {
​
  },
  async renamed (opts) {
​
  }
}
```

### Properties

* **key**: A short, unique and camelCase-formatted name for this module.
* **title**: The full name of the module.
* **props**: An object of user editable properties. See [Module Properties](properties.md) for more info.

### Events

#### activated

Upon activation of the storage module from the administration area. This is usually where storage prerequisites are checked _\(e.g. check settings, try to connect, create container, initialize repository, etc.\)._ 

```javascript
async activated (opts) { }
```

Any error thrown \(or returning a rejected promise\) will be reported to the user and the storage strategy will not be enabled.

#### deactivated

Upon deactivation of the storage module from the administration area. This is where you disconnect from the storage provider if required. You should **never delete any content** upon deactivation, as the user may choose to re-enable this storage strategy later or simply want to keep the current content as backup.

```javascript
async deactivated (opts) { }
```

Any error thrown \(or returning a rejected promise\) will be reported to the user and the storage strategy will not be disabled.

#### init

Upon initialization of Wiki.js \(both startups or restarts\) and directly after the `activated` event. This is useful to establish a connection in some storage strategies.

```javascript
async init (opts) { }
```

Any error thrown \(or returning a rejected promise\) will prevent the storage strategy from being used until Wiki.js is restarted or the error is acknowledged by the user in the administration area.

#### created

Upon creation of a new page.

```javascript
async created (opts) { }
```

Parameter **opts** is an object composed of the following properties:

```javascript
{
    id: Number, // Unique ID of the page
    path: String, // Unique path of the page (e.g. /some/page)
    title: String, // Title of the page
    description: String, // Short description of the page
    isPublished: Boolean, // Is the page published
    publishStartDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    publishEndDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    contentType: String, // The content original type (e.g. markdown, html, etc.)
    content: String, // The content
    createdAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    authorId: Number, // The Unique ID of the author
    authorName: String, // The full name of the author
    authorEmail: String // The email address of the author
}
```

#### updated

Upon modification of a page contents.

```javascript
async updated (opts) { }
```

Parameter **opts** is an object composed of the following properties:

```javascript
{
    id: Number, // Unique ID of the page
    path: String, // Unique path of the page (e.g. /some/page)
    title: String, // Title of the page
    description: String, // Short description of the page
    isPublished: Boolean, // Is the page published
    publishStartDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    publishEndDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    contentType: String, // The content original type (e.g. markdown, html, etc.)
    content: String, // The content
    createdAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    updatedAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    authorId: Number, // The Unique ID of the author (user updating the page)
    authorName: String, // The full name of the author (user updating the page)
    authorEmail: String, // The email address of the author (user updating the page)
    creatorId: Number, // The Unique ID of the user that first created the page
    creatorName: String, // The full name of the user that first created the page
    creatorEmail: String // The email address of the user that first created the page
}
```

#### deleted

Upon deletion of a page.

```javascript
async deleted (opts) { }
```

Parameter opts is an object composed of the following properties:

```javascript
{
    id: Number, // Unique ID of the page
    path: String, // Unique path of the page (e.g. /some/page)
    title: String, // Title of the page
    description: String, // Short description of the page
    createdAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    deletedAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    authorId: Number, // The Unique ID of the author (user deleting the page)
    authorName: String, // The full name of the author (user deleting the page)
    authorEmail: String, // The email address of the author (user deleting the page)
    creatorId: Number, // The Unique ID of the user that first created the page
    creatorName: String, // The full name of the user that first created the page
    creatorEmail: String // The email address of the user that first created the page
}
```

#### renamed

Upon rename of a page or when a page is moved to another location.

```javascript
async renamed (opts) { }
```

Parameter opts is an object composed of the following properties:

```javascript
{
    id: Number, // Unique ID of the page
    sourcePath: String, // Previous path of the page (e.g. /some/oldpage)
    destinationPath: String, // New path of the page (e.g. /some/newpage)
    title: String, // Title of the page
    description: String, // Short description of the page
    isPublished: Boolean, // Is the page published
    publishStartDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    publishEndDate: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    contentType: String, // The content original type (e.g. markdown, html, etc.)
    content: String, // The content
    createdAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    updatedAt: String, // ISO-8601 Date (YYYY-MM-DDTHH:mm:ss.sssZ)
    authorId: Number, // The Unique ID of the author (user renaming the page)
    authorName: String, // The full name of the author (user renaming the page)
    authorEmail: String, // The email address of the author (user renaming the page)
    creatorId: Number, // The Unique ID of the user that first created the page
    creatorName: String, // The full name of the user that first created the page
    creatorEmail: String // The email address of the user that first created the page
}
```

