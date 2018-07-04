# Installation

## Install

{% tabs %}
{% tab title="Linux" %}
**Create an empty folder** where Wiki.js should be installed.

From this folder, in a command prompt, **run** the following command:

```bash
curl -sSo- https://wiki.js.org/install.sh | bash
```

Wiki.js will be installed in the current directory.
{% endtab %}

{% tab title="macOS" %}
**Create an empty folder** where Wiki.js should be installed.

In Terminal, navigate to the folder you just created and **run** the following command:

```bash
curl -sSo- https://wiki.js.org/install.sh | bash
```

Wiki.js will be installed in the current directory.
{% endtab %}

{% tab title="Windows" %}
From a **PowerShell** prompt, run the following command:

```bash
iex ((New-Object System.Net.WebClient).DownloadString('https://wiki.js.org/install.ps1'))
```

You'll be prompted where Wiki.js should be installed. The destination folder will be created automatically if it doesn't exist.

{% hint style="info" %}
**Execution Policy**

Your powershell execution policy must be set to Bypass to allow this script to run:  
`Set-ExecutionPolicy Bypass`
{% endhint %}
{% endtab %}

{% tab title="Docker" %}
#### Using the official Docker image

```bash
sudo docker run -p 8080:3000 -v /home/bob/wiki-config.yml:/var/wiki/config.yml requarks/wiki
```

#### Using a custom Dockerfile

#### Using Docker Compose
{% endtab %}

{% tab title="Heroku" %}
Deploy a new Wiki.js instance on Heroku using the [install wizard](https://heroku.com/deploy?template=https://github.com/requarks/wiki-heroku).
{% endtab %}
{% endtabs %}



