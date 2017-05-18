# Exoframe (beta)

> Power armor for docker containers

[![Build Status](https://gitlab.com/exoframejs/exoframe/badges/master/build.svg)](https://gitlab.com/exoframejs/exoframe/pipelines)
[![coverage report](https://gitlab.com/exoframejs/exoframe/badges/master/coverage.svg)](https://gitlab.com/exoframejs/exoframe/commits/master)
[![npm](https://img.shields.io/npm/v/exoframe.svg?maxAge=2592000)](https://www.npmjs.com/package/exoframe)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://opensource.org/licenses/MIT)

[![asciicast](https://asciinema.org/a/121137.png)](https://asciinema.org/a/121137)

## How it works

Exoframe intends to do all the heavy lifting required to build and deploy web services for you.  
Exoframe uses [Docker](https://www.docker.com/) to deploy your project and [Traefik](https://traefik.io/) to proxy them to requested domain and/or paths.  
All the configuration of your projects happens automatically. So after running the command, the only thing you need to do is wait a few seconds until your files have been built or deployed!

Currently, Exoframe understands and can deploy the following project types:

1. static html based projects - will be deployed using [nginx](http://hub.docker.com/_/nginx) image
2. node.js based projects - will be deployed using [node:alpine](https://hub.docker.com/_/node) image
3. docker based project - will be deployed using your [Dockerfile](https://docs.docker.com/engine/reference/builder/)
4. docker-compose based project - will be deployed using your [docker-compose](https://docs.docker.com/compose/compose-file/) file

To run Exoframe you need two parts - Exoframe CLI on your local machine and [Exoframe server](https://github.com/exoframejs/exoframe-server) on your server with Docker.

## Installation and Usage

Install Exoframe CLI (needs at least node v6):

```
npm install exoframe -g
```

Make sure you have [Exoframe server](https://github.com/exoframejs/exoframe-server) deployed, set it as your endpoint using:

```
exoframe endpoint http://you.server.url
```

Then use it:

```
exoframe <command> [options]
```

You can find a list of all commands and options below.

### Commands

| Command                | Description |
| ---------------------- | ----------- |
| deploy [path]          | Deploy specified path using Exoframe |
| list                   | List currently deployed projects |
| rm [project]           | Remove existing project |
| login                  | Login into Exoframe server |
| endpoint [url]         | Gets or sets the endpoint of Exoframe server |
| completion             | Generates bash completion script  |

## Configuration

Exoframe stores its config in `~/.exoframe/cli.config.yml`.  
Currently it contains endpoint URL and list of template plugins:

```yaml
endpoint: 'http://localhost:8080' # your endpoint URL, defaults to localhost
```

## Contribute

1. Fork this repository to your own GitHub account and then clone it to your local device.
2. Uninstall exoframe if it's already installed: `npm uninstall exoframe -g`
3. Link it to the global module directory: `npm link`
4. Transpile the source code and watch for changes: `npm start`

Now can use the `exoframe` command everywhere.

## License

Licensed under MIT.
