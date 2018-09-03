---
description: Guide on connecting to various Git providers
---

# Git

## What is Git

Git is a version control system \(VCS\) that is used mainly for software development and other version control tasks. As a distributed revision control system it is aimed at speed, data integrity, and support for distributed, non-linear workflows. In other words, it backups and keeps track of everything you add, modify or delete in a repository.

## Why do I need it?

Because the documentation you write should always be stored in a safe location. Even though databases and file storage can be configured to have backups, they are either costly or completely ineffective. Storing documents into a Git repository not only make sense, it's cost effective \(free in most cases\), fast and safe.

Having all your documentation in a central Git repository means you control 100% of your data at all times.

* Want to modify content outside the Wiki? **You can**.
* Want to transfer content somewhere else? **You can**.
* You want to completely stop using Wiki.js? Hopefully not, but should you want to, **you can** and there's nothing to extract or backup because everything is already in that Git repository.

## Providers

There's quite an extensive list of Git providers, but we'll focus on the 4 major ones, which all offer free repository hosting.

### GitHub

Public: **Yes \(free\)**  
Private: **Paid only**  
Supported authentication methods: **SSH and Basic**

{% embed data="{\"url\":\"https://github.com/\",\"type\":\"link\",\"title\":\"Build software better, together\",\"description\":\"GitHub is where people build software. More than 27 million people use GitHub to discover, fork, and contribute to over 80 million projects.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://assets-cdn.github.com/images/modules/open\_graph/github-logo.png\",\"width\":1200,\"height\":1200,\"aspectRatio\":1}}" %}

#### Using SSH \(Repository\)

{% hint style="success" %}
 This method gives access only to the repository, which is the recommended way.
{% endhint %}

* From the repository **Settings** page, select **Deploy Keys** in the sidebar.
* Click the **Add deploy key** button.
* Enter a **title** for the key \(e.g. Wiki.js\).
* Enter your **public key** content in the textbox. Learn how to [create a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).
* Check the box \[x\] **Allow write access**.
* **Save** the key.
* Follow the instructions for SSH below.

#### Using SSH \(Global\)

{% hint style="warning" %}
This method gives access to all repository owned by the account. Do not use unless you know what you're doing!
{% endhint %}

* From the user dropdown menu, click **Settings** and select **SSH and GPG Keys** in the sidebar.
* Click the **New SSH Key** button.
* Enter a **title** for the key \(e.g. Wiki.js\).
* Enter your **public key** content in the textbox. Learn how to [create a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).
* **Save** the key.
* Follow the instructions for SSH below.

#### Using Basic Authentication

{% hint style="warning" %}
This method gives access to all repository owned by the account. Do not use unless you know what you're doing! This method is also less secure than using SSH keys.
{% endhint %}

* From the **Settings** page, select **Personal Access Tokens** in the sidebar.
* Click on **Generate New Token**.
* Enter a description for this token \(e.g. Wiki.js\) and enable the **repo** permissions.
* Follow the instructions for Basic below.

### GitLab

Public: **Yes \(free\)**  
Private: **Yes \(free\)**  
Supported authentication methods: **SSH and Basic**

{% embed data="{\"url\":\"https://gitlab.com/\",\"type\":\"link\",\"title\":\"The only single product for the complete DevOps lifecycle - GitLab\",\"description\":\"“GitLab is the leading integrated product for modern software development. Connecting issue management, version control, code review, CI, CD, and monitoring into a single, easy-to-install application, we help teams go faster from planning to monitoring.”\",\"icon\":{\"type\":\"icon\",\"url\":\"https://about.gitlab.com/ico/favicon-192x192.png\",\"width\":192,\"height\":192,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://about.gitlab.com/images/blogimages/gitlab-blog-cover.png\",\"width\":1750,\"height\":1225,\"aspectRatio\":0.7}}" %}

#### Using SSH \(Repository\)

{% hint style="success" %}
 This method gives access only to the repository, which is the recommended way.
{% endhint %}

* From the a project page, select **Deploy Keys** from the Settings dropdown menu.
* Enter a **title** for the key \(e.g. Wiki.js\).
* Enter your **public key** content in the textbox. Learn how to [create a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).
* Check the box \[x\] **Write access allowed**.
* **Save** the key.
* Follow the instructions for SSH below.

#### Using SSH \(Global\)

{% hint style="warning" %}
This method gives access to all repository owned by the account. Do not use unless you know what you're doing!
{% endhint %}

* From the user dropdown menu, click **Settings** and select **SSH Keys** from the top menu.
* Enter your **public key** content in the textbox. Learn how to [create a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).
* Enter a **title** for the key \(e.g. Wiki.js\).
* **Save** the key.
* Follow the instructions for SSH below.

#### Using Basic Authentication

{% hint style="warning" %}
This method gives access to all repository owned by the account. Do not use unless you know what you're doing! This method is also less secure than using SSH keys.
{% endhint %}

* From the **Settings** page, select **Access Tokens** from the top menu.
* Enter a **name** and **expiration** for this token \(e.g. Wiki.js\) and enable all permission scopes.
* **Save** the token.
* Follow the instructions for Basic below.

### Bitbucket

Public: **Yes \(free, up to 5 users\)**  
Private: **Yes \(free, up to 5 users\)**  
Supported authentication methods: **SSH and Basic**

{% embed data="{\"url\":\"https://bitbucket.org/\",\"type\":\"link\",\"title\":\"Bitbucket \| The Git solution for professional teams\",\"description\":\"Collaborate on code with inline comments and pull requests. Manage and share your Git repositories to build and ship software, as a team.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://bitbucket-marketing-cdn.atlassian.com/assets/img/favicons/bitbucket/apple-touch-icon.png\",\"width\":180,\"height\":180,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://bitbucket-marketing-cdn.atlassian.com/dam/jcr:1437c132-1dbc-410d-b6a6-cb7fce8f2775/bitbucket\_rgb\_darkblue\_atlassian\_1200x630.png\",\"width\":1200,\"height\":630,\"aspectRatio\":0.525}}" %}

### Visual Studio Team Services

Public: **No**  
Private: **Yes \(free, up to 5 users\)**  
Supported authentication methods: **SSH and Basic**

{% embed data="{\"url\":\"https://visualstudio.com/\",\"type\":\"link\",\"title\":\"Visual Studio IDE, Code Editor, VSTS, & App Center\",\"description\":\"Visual Studio dev tools & services make app development easy for any platform & language. Try our Mac & Windows code editor, IDE, or VSTS for free.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.visualstudio.com/wp-content/uploads/2017/02/BrandVisualStudioIDE2017RTW\_64x.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://www.visualstudio.com/wp-content/uploads/2017/03/AttachFileHandler.png\",\"width\":800,\"height\":418,\"aspectRatio\":0.5225}}" %}

#### Using SSH

{% hint style="success" %}
 This method is more secure than using password-based authentication methods, which is the recommended way.
{% endhint %}

* From User dropdown menu, select **Security**.
* Click on **SSH Public Keys** from the left sidebar.
* Click on the **Add** button.
* Enter a **title** for the key \(e.g. Wiki.js\).
* Enter your **public key** content in the textbox. Learn how to [create a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).
* **Save** the key.
* Follow the instructions for SSH below.

#### Using Basic \(Personal Access Tokens\)

* From User dropdown menu, select **Security**.
* Click on **Personal Access Tokens** from the left sidebar.
* Click on the **Add** button.
* Enter a **description** for the key \(e.g. Wiki.js\) and set the desired **expiration date**.
* Check \[x\] the follow authorized scopes: **Code \(read, write and manage\)** and **Code \(status\)**.
* **Create** the token.
* Follow the instructions for Basic below.

#### Using Basic \(Alternate Credentials\)

* From User dropdown menu, select **Security**.
* Click on **Personal Authentication Credentials** from the left sidebar.
* Check \[x\] the **Enable alternate authentication credentials** checkbox.
* Enter a **username** and **password**.
* **Save** the login.
* Follow the instructions for Basic below.

## Configure Wiki.js

Now that your repository is setup using the instructions above, it's time to enter the info in the configuration file. Different parameters are required depending on the authentication type:

### Common

Set the **sslVerify** parameter to `false` if the Git repository is using an SSL certificate that can't be verified by Wiki.js \(e.g. self-signed or expired certificates\). Setting it to false is obviously not recommended and a security risk.

The **signature** block is required and must be identical to the account info of your Git provider. For example, if using Github, you must put your name and email exactly as entered in your GitHub profile.

Example:

```yaml
git:
  url: https://server.com/org/repo
  branch: master
  auth:
    
    # Type: basic or ssh
    type: ssh
        
    # Only for Basic authentication:
    username: marty@doc.com
    password: MartyMcFly88
        
    # Only for SSH authentication:
    privateKey: /etc/wiki/keys/git-private.pem
        
    # Check for valid SSL certificate
    sslVerify: true
        
  signature:
    name: Marty
    email: marty@doc.com
```

### Using SSH

You must define private key \(**privateKey**\) location when using the SSH authentication method. The private key must **NOT** be protected by a passphrase. If you want to a passphrase, you must configure your ssh-agent to handle it. Wiki.js will use the standard ssh executable installed on your system.

Example:

```yaml
git:
  url: git@server.com:org/repo.git
  branch: master
  auth:
    type: ssh
    privateKey: /etc/wiki/keys/git-private.pem
    sslVerify: true
  signature:
    name: Marty
    email: marty@doc.com
```

### Using Basic \(User/Pass or Token\)

Using a standard username and password/token combination. Make sure to use a long and strong password.

Example:

```yaml
git:
  url: https://server.com/org/repo
  branch: master
  auth:
    type: basic
    username: marty@doc.com
    password: MartyMcFly88
    sslVerify: true
  signature:
    name: Marty
    email: marty@doc.com
```

## Using an existing repository

You can use an existing repository \(from an existing Wiki.js installation or any standard markdown-based documentation system\), as long as the filenames match the requirements below. The existing content will be fetched during the first sync.

* All markdown files \(.md\) and folders are in lowercase \(including the file extension\).
* All markdown files \(.md\) and folders use the hyphen `-` to separate words. e.g. `sample-file-tutorial.md`

You can leave the `README.md` file as is; it will be ignored by Wiki.js.

## Disable remote sync

It is **highly recommended** to have remote sync enabled for backups and changes tracking purposes. It can however be disabled should you want to by setting `git: false` in your `config.yml` file:

```yaml
# Remote sync disabled:

git: false

# Remote sync enabled:

git:
  url: https://github.com/Organization/Repo
  branch: master
  auth:
    type: ssh
    privateKey: /etc/wiki/keys/git.pem
    sslVerify: true
  signature:
    name: Marty
    email: marty@example.com
```

{% hint style="danger" %}
When using docker, make sure to have a proper backup strategy or to mount the `/var/wiki/repo` directory outside the container so that your content is preserved in the event the container is recreated.
{% endhint %}

