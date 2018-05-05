---
description: How to upgrade to the latest version of Wiki.js
---

# Upgrade

## Before upgrading

* Your Wiki.js installation will not be accessible during the upgrade process.
* No content will be lost. However, users should stop editing content and save their changes before starting the upgrade.
* Verify that all content have been synced to the remote git repository.
* Read the release notes of the latest release carefully, in case special upgrade instructions steps are provided.

## Upgrade

1. Make a backup of your `config.yml` to a secure location.
2. Delete all files and folders in your Wiki.js installation folder _\(including the /data and /repo folders, these will be generated again automatically\)_.
3. [Install the latest version](installation/).
4. Copy your `config.yml` backup file to its original location, at the root of your Wiki.js installation folder.
5. Start Wiki.js: `node wiki start`

