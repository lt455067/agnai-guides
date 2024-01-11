---
title: "Running AGNai Locally"
layout: default
nav_order: 6
---
# Running AGNai Locally

Instead of using Agnai as an online service, you can run it locally on your machine. Before you try it, take the following into account:
* You can use the online Agnai anonymously without being logged in, this way any data will be stored in your local browser memory. `Anonymous` users have their data saved to the browser's local storage. Your data will "persist", but not be shareable between devices or other browsers. Clearing your browser's application data/cookies will delete this data.
* You will run Agnai locally, but you will still need to connect to a remote AI service, unless you intend to run the AI model yourself.
* Locally-hosted Agnai doesn't give you access to Agnai models, even if you're a subscriber (this might change in the future).

If you want to run Agnai locally, there are 3 different ways you can choose from:
* Run Agnai in a docker container.
* Install Agnai as an `npm` application.
* Create a full development environment, if you want to make changes to the code and contribute to Agnai development.

Additional optional components:
* MongoDB (**recommended**) - necessary to enable permanent storage for user data, characters, chats, etc. If it is not installed, Agnai will run in `anonymous-only` mode (see above).
* Redis (not recommended) - necessary for multiple Agnai nodes to communicate with each other, not necessary in most cases.
## Installing in a Docker container
If you're familiar with running applications in Docker, this is probably the easiest way to install the application:
1. Install [Docker](https://www.docker.com/get-started/).
2. Either clone the whole [repository](https://github.com/agnaistic/agnai) or download the [self-host.docker-compose.yml](https://github.com/agnaistic/agnai/blob/dev/self-host.docker-compose.yml) file.
3. Run the following command where the `yml` file is located:
```
docker compose -p agnai -f self-host.docker-compose.yml up -d
```

This will install the latest version of both Agnai and MongoDB inside the Docker container. You can access the application by opening [http://localhost:3001](http://localhost:3001) in your browser. You should be able to log in with the initial credentials: `admin` / `password`.

### Updating the application
To update the application to the latest available version:
1. Navigate to the directory where the `yml` file is located.
2. Pull the latest version of the containers by running:
```
docker compose -f self-host.docker-compose.yml pull
```
3. Restart the containers:
```
docker compose -p agnai -f self-host.docker-compose.yml up -d
```
## Installing the NPM package
This will install Agnai as a global `npm` application. You will still need to manually install MongoDB if necessary.
1. Install [Node.js](https://nodejs.org/en/download/).
2. Install [MongoDB](https://www.mongodb.com/docs/manual/installation/) (this step is optional, but heavily recommended, see above).
3. Either clone the whole [repository](https://github.com/agnaistic/agnai) or download the [.env.template](https://github.com/agnaistic/agnai/blob/dev/.env.template) file.
4. Rename the `.env.template` file to `.env` and open it in the editor. Change the parameters as needed, the most important ones are:
	* `INITIAL_USER`, `INITIAL_PASSWORD` will let you set the initial credentials to log in to the application for the first time.
	* `DB_HOST`, `DB_PORT`, `DB_NAME` - MongoDB database parameters.
5. Install the `dotenv-cli` tool from `npm` - this tool will let you load variables from your `.env` file
```
npm install -g dotenv-cli
```
6. Run the following command to install the application:
```
npm install agnai -g
```
7. Run the application and pass the `.env` file:
```
dotenv -e .env agnai
```
You can access the application by opening [http://localhost:3001](http://localhost:3001) in your browser.

You can also pass additional parameters to the application, to check the available parameters, run:
```
agnai --help
```
### Updating the application
To update the application to the latest published version:
1. Stop Agnai.
2. Run the following command:
```
npm update -g agnai
```
3. Start Agnai again.
## Development environment
To create a full development environment for AGNai, please follow the directions in the [README](https://github.com/agnaistic/agnai/blob/dev/README.md) file in the repository.
