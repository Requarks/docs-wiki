# Getting Started

There are 2 methods to develop for Wiki.js. You can either use the dockerized development environment _\(recommended\)_ or install all dependencies manually on your machine.

## Using Docker

### Prerequisites

* docker
* docker-compose

### Run the project

1. Clone the project from GitHub \(make sure to use the `dev` branch\).
2. Start the development environment:
   * On Linux / macOS: `make docker-dev-up`
     * _You may need to start the above command with `sudo` depending on your OS configuration._
   * On Windows: `npm run docker:dev:up`
     * _This assumes you have Node.js installed on your machine._
3. Wait for the initialization to complete. This **may take a while the very first time** as the wiki container image must be built. Subsequent startups will be extremely fast.
4. Browse to **http://localhost:3000/** _\(replace localhost with the hostname of your machine if applicable\)_.
5. Complete the setup wizard to finish the installation.

### Stopping the project

When you're done and no longer need the development environment. Simply run the following command to stop and remove the containers:

* On Linux / maxOS: `make docker-dev-down`
  * _You may need to start the above command with `sudo` depending on your OS configuration._
* On Windows: `npm run docker:dev:down`
  * _This assumes you have Node.js installed on your machine._

### Other Commands

| Command | Description |
| :--- | :--- |
| docker-dev-up | Starts the development environment. |
| docker-dev-down | Stops and remove the development environment. |
| docker-dev-rebuild | Rebuilds the wiki container image. |
| docker-build | Builds the client assets files using a temporary environment. |

On Windows, replace the `-` with `:` in the commands above when using npm tasks.  
_e.g._ `docker-dev-rebuild` becomes `docker:dev:rebuild`

## Manually

### Prerequisites

* All standard Wiki.js [prerequisites](../installation/prerequisites.md)
* Yarn 1.x \(`npm i -g yarn`\)
* Native compilation dependencies
  * Ubuntu:  `apt-get install build-essential`
  * Windows: from an administrator Powershell: `npm i -g --production windows-build-tools`

### Installing the project

1. Clone the project from GitHub \(make sure to use the `dev` branch\).
2. From the project folder, run the command:

   `yarn`  
   This will install all necessary dependencies.

3. Rename `config.sample.yml` to `config.yml`.
4. Edit `config.yml` with your local dev machine settings \(db, redis, etc.\)

### Run the project

From the project folder, simply run `npm run dev`

This will start Wiki.js in dev mode. Client assets are compiled first \(using Webpack\), then the server will start automatically. Wait for this process to complete before loading the app!

Browse to the site, using the configuration you defined in `config.yml`. For example, if using port 3000 on your local machine, you would browse to http://127.0.0.1:3000/.

The first time you load the wiki, you'll get greeted with the setup wizard. Complete all the steps to finish the installation.

## Notes

### Recommended IDE

Wiki.js is built using [Visual Studio Code](https://code.visualstudio.com) and comes with pre-defined extension recommendations, project settings and debug configuration. You can use your favorite IDE but Visual Studio Code is highly recommended.

### Development

Any changes made to client files will automatically trigger a build and the site will be updated live automatically. If the changes cannot be replaced inline, the page will reload automatically.

Any changes made to the server files will automatically trigger a server restart. You can also force a restart by typing `rs` in the terminal followed by **Enter**.

To stop the development server, use **CTRL-C** until the process exits.

