
<div align="center">
<p align="center">
  <img src="https://user-images.githubusercontent.com/44535256/180598361-505e938a-dff5-4845-9fb7-6f0a7b8d0682.png" alt="Logo"/>
</p>

<p align="center">
  <a href="https://twitter.com/helloburaste">
    <img alt="Twitter: Hello Buraste" src="https://img.shields.io/twitter/follow/helloburaste?style=social" target="_blank" />
  </a>
</p>
<p style="margin-top: 0;">Dockerize your Strapi v4 backend with Next.js and Nginx Support 🚀</p>
	</div>

## Table of Contents <!-- omit in toc -->

- [Current Status](#current-status)
- [What for?](#what-for)
- [Features & Stacks](#features--stacks)
    - [Backend](#backend)
    - [Frontend](#frontend)
    - [Database](#database)
    - [Reverse Proxy](#reverse-proxy)
    - [Containerization](#containerization)
    - [Environment Variables Management](#environment-variables-management)
- [Installation and Usage](#installation-and-usage)
    - [Installation](#installation)
    - [Usage](#usage)
- [Security for Endpoints](#security-for-endpoints)
- [Contributing](#contributing)
- [Authors](#authors)
- [License](#license)

## Current Status

This package is currently under development and should be consider **BETA** in terms of state. We are currently accepting contributions to help develop and maintain this package.

For more information on contributing please see [the contrib message below](#contributing).

##  What for?

- Easy development & production environment
- Easy frontend adoption (just delete frontend folder and create your best)
- Creating full-stack applications for small or medium size projects

## Features & Stacks

#### Backend
- Strapi v4
- Node.js v16 for Docker Image
- Yarn package manager
#### Frontend
- Next.js v12.2
- React.js v18.2
- Typescript v4.7
- Node.js-alpine for Docker Image
- Yarn package manager
#### Database
- Postgres v12-alpine
- Linux/amd64 platform for platform error on Apple M1 chips
- Named volumes
#### Reverse Proxy
- Nginx Latest
- Fastcgi support
- Mime-types
- Security configs
#### Containerization
- Docker-compose v3 for container orchestration 🐳
- Seperated Dockerfiles for development and production
#### Environment Variables Management
- One file for backend + frontend + database + nginx


## Installation and Usage
You have to currently exist Docker and Docker Compose on your system:
- [Docker & Docker Compose](https://docs.docker.com/get-docker/)

#### Installation
- Clone the repo
- Copy `.env.example` file to `.env`
- Change credentials with secure and strong ones
- If you are on development, be sure `ENVIRONMENT=development` on .env file
- If you are on production or want to production build, change with `ENVIRONMENT=production`
- Be sure `localhost:80` is accesible and not using from another process (Nginx runs on 80)
- Pull necessary images:
```bash
docker-compose pull
```
#### Usage
- Build and up your docker-compose file if everything is ok:
```bash
docker-compose build && docker-compose up -d
```
- Now you can access to Next.js frontend on `http://localhost` and Strapi backend (admin) on `http://localhost/strapi/admin`
- Register with your e-mail and password.
- Go to `Content-Type Builder`, It has sample content type as `Article` and this content type has three field as `title` `body` and `cover`.
- For creating new `Article`, go to `Content Manager`and click `Article`on left pane, click `Create new entry`and fill the blanks > click Publish!
- For testing API endpoint you need to give public access to the `Article` so
	- Go to `Settings`>`User & Permissions Plugin`>`Roles`>`Public`>`Article`and select `find` `findOne`, If you need more, select what you want and save!
	- Go to the `http://localhost/strapi/api/articles`

## Security for Endpoints
Secure all your Strapi related endpoints in Nginx, make sure to use API tokens to connect to the backend and keep this information private. The Nginx config that on the repo is for development, not production ⛔️

## Contributing

We are always welcome for contributions to help shape this package.

If interested please feel free to email the maintainer Burak at: hello@buraste.com

## Authors

- Burak Ibis:
	- Github: [@buraste](https://github.com/buraste)
	- Twitter: [@helloburaste](https://twitter.com/helloburaste)

## License

See the [LICENSE](./LICENSE.md) file for licensing information.
