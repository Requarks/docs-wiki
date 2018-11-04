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
docker run -d -p 8080:3000 --name wiki --restart unless-stopped requarks/wiki:dev
```

#### Environment Variables

* **PORT** : Port to listen to \(HTTP\)
* **DB\_TYPE** : Type of database \(`mysql`, `postgres`, `mariadb`, `mssql` or `sqlite`\)
* **DB\_HOST** : Hostname or IP of the database
* **DB\_PORT** : Port of the database
* **DB\_USER** : Username to connect to the database
* **DB\_PASS** : Password to connect to the database
* **DB\_NAME** : Database name
* **DB\_FILEPATH** : Path to the SQLite file _\(SQLite only\)_
* **REDIS\_HOST** : Hostname or IP of the redis instance
* **REDIS\_PORT** : Port of the redis instance
* **REDIS\_DB** : Database Index of the redis instance _\(number\)_
* **REDIS\_PASSWORD** : Password to connect to the redis instance _\(optional\)_

#### Using Docker Compose

Here's an example of a Docker Compose file with Redis and PostgreSQL dependencies:

{% code-tabs %}
{% code-tabs-item title="docker-compose.yml" %}
```yaml
version: "3"
services:

  redis:
    image: redis:4-alpine
    ports:
      - "6379:6379"
    logging:
      driver: "none"
    networks:
      - wikinet

  db:
    image: postgres:9-alpine
    environment:
      POSTGRES_DB: wiki
      POSTGRES_PASSWORD: wikijsrocks
      POSTGRES_USER: wikijs
    logging:
      driver: "none"
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - wikinet
    ports:
      - "5432:5432"

  wiki:
    image: requarks/wiki
    depends_on:
      - db
      - redis
    environment:
      PORT: 3000
      DB_TYPE: postgres
      DB_HOST: db
      DB_PORT: 5432
      DB_USER: wikijs
      DB_PASS: wikijsrocks
      DB_NAME: wiki
      REDIS_HOST: redis
      REDIS_PORT: 6379
      REDIS_DB: 0
    networks:
      - wikinet
    ports:
      - "3000:3000"

networks:
  wikinet:

volumes:
  db-data:

```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Heroku" %}
Deploy a new Wiki.js instance on Heroku using the [install wizard](https://heroku.com/deploy?template=https://github.com/requarks/wiki-heroku).
{% endtab %}
{% endtabs %}



