---
description: Install Wiki.js on Docker
---

# Docker

## Using the Docker Image

This is the most direct and simple way to run a Docker container of Wiki.js. For more control and flexibility over its configuration, check out the [Dockerfile ](docker.md#using-a-dockerfile)and [Docker Compose](docker.md#using-docker-compose) guides below.

### Prerequisites

* Docker
* A MongoDB database server \(either running inside another container or on a remote machine\)

### Create config file

1. Create a copy of the [sample config file](https://github.com/Requarks/wiki/blob/master/config.sample.yml) on your host.
2. Modify the config file with your own settings.

###  Install

####  Fetch image

```bash
sudo docker pull requarks/wiki
```

#### Run container

You must provide 3 parameters when running a Wiki.js container:

* The port to expose
* The administrator account email
* The path of the config file created earlier

Adapt the example command below:

```bash
sudo docker run -p 8080:3000 -e "WIKI_ADMIN_EMAIL=admin@example.com" -v /home/bob/wiki-config.yml:/var/wiki/config.yml requarks/wiki
```

In the example above, the port `3000` is the port defined in your `config.yml`, while `8080` is the port that is exposed publicly. The admin email is set to `admin@example.com`. The path to the config.yml file is set to `/home/bob/wiki-config.yml`. Do **not** change the path in the container \(`/var/wiki/config.yml`\)!

#### First login

An administrator account is created the first time you run the container. The default password is `admin123`. Change it upon login!

## Using a Dockerfile

### Prerequisites

* Docker
* A MongoDB database server \(either running inside another container or on a remote machine\)

### Create config file

1. Create a copy of the [sample config file](https://github.com/Requarks/wiki/blob/master/config.sample.yml) on your host.
2. Modify the config file with your own settings.

###  Create Dockerfile

1. Create a copy of the [sample Dockerfile](https://github.com/Requarks/wiki/blob/master/tools/Dockerfile).
2. Replace the `WIKI_ADMIN_EMAIL` parameter value with the email of the administrator account. This account will be created when run the first time.
3. Replace the `your-config.yml` value with the name of your config file created earlier. This file must be located in the same folder as your Dockerfile if not providing the full path. It will be copied inside your docker container.
4. Change the `EXPOSE` port to match the port entered in your config.yml file.

###  Build the image

From a command prompt in the same folder as your Dockerfile, execute the following command to build your Dockerfile:

```bash
sudo docker build -t wiki .
```

### Run the container

It's now time to run the container from the image created in the previous step:

```bash
sudo docker run -p 8080:3000 wiki
```

The `-p` parameter above is optional. Define it if you want to re-map the exposed port to something else.

###  First login

An administrator account is created the first time you run the container. The default password is `admin123`. Change it upon login!

## Using Docker Compose

### Prerequisites

* Docker

###  Create config file

1. Create a copy of the [sample config file](https://github.com/Requarks/wiki/blob/master/config.sample.yml) on your host.
2. Modify the config file with your own settings.

Make sure to set the `db` parameter to point to the mongo container. In the example docker compose file, the mongo container is named `wikidb`. As such, the `db` connection string should be set to: `mongodb://wikidb:27017/wiki`

###  Create Docker Compose file

1. Create a copy of the [sample Docker Compose](https://github.com/Requarks/wiki/blob/master/tools/docker-compose.yml) file.
2. Change the `ports` port to match the port entered in your config.yml file.
3. Replace the `WIKI_ADMIN_EMAIL` parameter value with the email of the administrator account. This account will be created when run the first time.
4. Replace the `./config.yml` value with the path of your config file created earlier. It will be linked to your docker container. Do **not** change the path of the config file inside the container \(`/var/wiki/config.yml`\)!
5. Change the local path of the MongoDB data folder \(`./data/mongo`\) if necessary. Do **not** change the path of the data folder inside the mongo container \(`/db/data`\)!

###  Run the container

It's now time to run the containers as defined in the previous step:

```bash
sudo docker-compose up
```

### First login

An administrator account is created the first time you run the container. The default password is `admin123`. Change it upon login!

