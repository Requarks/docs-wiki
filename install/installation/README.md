---
description: How to install Wiki.js on your server
---

# Installation

## Prerequisites

 Make sure you have read the [prerequisites ](../prerequisites.md)page to ensure your server meets the minimum requirements.

## Installation

### Linux / macOS

**Create an empty folder** where Wiki.js should be installed.

From this folder, in a command prompt, **run** the following command:

```bash
curl -sSo- https://wiki.js.org/install.sh | bash
```

Wiki.js will be installed in the current directory.

### Windows

From a **PowerShell** prompt, **run** the following command:

```csharp
iex ((New-Object System.Net.WebClient).DownloadString('https://wiki.js.org/install.ps1'))
```

You'll be prompted where Wiki.js should be installed. The destination folder will be created automatically if it doesn't exist.

{% hint style="info" %}
**Execution Policy**

Your powershell execution policy must be set to Bypass to allow this script to run:  
`Set-ExecutionPolicy Bypass`
{% endhint %}

## Configuration

Once the installation is completed, you'll be prompted to run the configuration wizard.

To start the configuration wizard manually, run the command `node wiki configure`. To use a custom port, use the following command: `node wiki configure 1234` where 1234 is the custom port.

Using your web browser, navigate to [http://localhost:3000/](http://localhost:3000/) \(replace `localhost` with the IP of your server / custom port if applicable\) and follow the on-screen instructions.

All settings entered during the configuration wizard are saved in the file `config.yml`. See the [Configuration File](https://docs-legacy.requarks.io/wiki/install/configuration) guide for all the possible options you can use.

## Run Wiki.js

The configuration wizard will automatically start Wiki.js for you.

To start Wiki.js manually, in a command prompt, **run** the following command: `node wiki start`  
- If using a Powershell prompt \(default on Windows 10\), you can instead use the `.\wiki start` command.  
- **Wait** for the command to complete. This can take several seconds.  
- **Browse** to your Wiki from your browser. You should see the Wiki.js welcome screen.

{% hint style="info" %}
 Wiki.js runs as a background process, using [pm2](http://pm2.keymetrics.io/) as its process manager.
{% endhint %}

