# Prerequisites

## Host Requirements

### OS

Wiki.js runs on virtually any system where Node.js is supported. This means it runs on **Linux**, **macOS**, **Windows** as well as container solutions such as **Docker** and **Heroku**.

### CPU

Wiki.js runs perfectly fine on a single CPU core. However, 2 cores or more are recommended to fully make use of the background workers.

### RAM

Linux systems should have at least **768 MB** of RAM to run Wiki.js. Windows and macOS systems usually require more RAM.

### Storage

Storage requirements are based on the content you will enter. Wikis that consists almost exclusively of text are not likely to exceed a few megabytes. However, as soon as you upload images, videos or other files, you should plan your storage requirements accordingly.

At least **1 GB** of storage dedicated to Wiki.js is recommended.

## Software Requirements

### Node.js

Node.js **8.11** or later is required. Wiki.js will not run on older versions such as 6.x or 4.x!

* ​[Official Website](https://nodejs.org/)​
* ​[Installation using the package manager \(Linux\)](https://nodejs.org/en/download/package-manager/)​

### Database

Wiki.js is compatible with the following database systems:

* MySQL **8.0** or later
* MariaDB **10.2.7** or later
* PostgreSQL **9.5** or later
* SQLite **3.9** or later

### Redis

Redis **3.2** or later is required.

## End-User Requirements

The following browsers are supported:

* Google Chrome _\(including Android version\)_
* Mozilla Firefox
* Microsoft Edge
* Microsoft Internet Explorer 11
* Apple Safari _\(including iOS version\)_

Note that only the latest version of these browsers are supported. All browsers \(with the exception of IE 11\) updates automatically in the background.

