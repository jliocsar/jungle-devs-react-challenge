<h1 align="center">Jungle Devs - React Challenge #001</h1>

<div align="center">

  [![Vercel](https://img.shields.io/badge/vercel%20-%23000000.svg?&style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com)
  [![Next.js](https://img.shields.io/badge/next%20js%20-%23000000.svg?&style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org)
  [![React.js](https://img.shields.io/badge/react%20-%2320232a.svg?&style=for-the-badge&logo=react&logoColor=%2361DAFB)](https://reactjs.org)
  [![Docker](https://img.shields.io/badge/docker%20-%230db7ed.svg?&style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com)

  ![Website preview](/.github/website.png)

  **[Live Preview](https://jungle-devs-react-challenge.vercel.app)**

</div>

## 📖 Description

This project is the implementation of Jungle Devs' React Challenge #001: a simplified version of Hapu’s ‘Become a Nanny Share Host’ made w/ React and Next.js.

---

## 🔥 Features

  - React + Next.js, delivering blazing fast server-side rendered pages;
  - Form validation using React Hook Forms and React's Context API, displaying clear response messages to the user;
  - Mobile first development, fully responsive from 320px to 4k screens;
  - Made focusing on SEO and a11y;
  - Easy and fast deploy w/ Docker;

---

## 🕑 Changelog

  - Day 1: Mobile layout;
  - Day 2: Desktop layout;
  - Day 3: Form integration (making POST requests properly);
  - Day 4: Errors handling & submit loading state;
  - Day 5: Hero's A/B test;
  - Day 6: Express custom server;
  - Day 7: Docker related files;
  - Day 8: Meta tags & final tweaks;
  - Day 9: Vercel deploy.

---

## 📌 Instructions

### Development

#### Installing dependencies

```sh
# using npm
npm install

# using yarn
yarn
```

#### Running the dev server

```sh
# using npm
npm run dev

# using yarn
yarn dev
```

---

### Production


There are many ways to deploy this application.

The first one is building the application and starting it using Next's custom server, which is powered by Express.

#### 🤖 Custom server

This is the way Docker will build and run the application, but you can use your own web server (e.g. Nginx) and reverse proxy the custom server port.

The server will run on port 3000 by default, but you can provide your own environment variable `SERVER_PORT` using a ```.env.local``` file.

Also, if you put your ```key.pem``` and ```cert.pem``` files in the project's root directory, the server will start with HTTPS on.

##### Installing dependencies

```sh
# using npm
npm install

# using yarn
yarn
```

##### Building the application

```sh
# using npm
npm run build

# using yarn
yarn build
```

##### Running the custom server

```sh
# using npm
npm run prod:start

# using yarn
yarn prod:start
```

#### 🐳 Docker

To run this application using Docker, you can either build and run it from Docker itself, or just use Compose to start with a single command.

Keep in mind that Docker will start the server at port 3000 and map the server to the host's 443 port by default.

You may also provide your own ```key.pem``` and ```cert.pem``` files in the project's root here, the container will copy it and start with HTTPS normally.

##### Docker build/run

```sh
# might need to run as sudo
docker build . -t jungle-devs-react-challenge
# make sure to provide 443:3000, as these are the default ports
docker run -p 443:3000 jungle-devs-react-challenge
```

You can run this with --env-file, for example:

```sh
# you can use the -d flag if you want to run it detached (as a background process)
docker run --env-file .env.production.local --name jd-react-challenge -p HOST_PORT:SERVER_PORT jungle-devs-react-challenge
```

##### Compose

```sh
# might need to run as sudo
docker-compose up
```

You can also run this one with --env-file:

```sh
# make sure to re-build if you ran up before, for example:
docker-compose --env-file .env.production.local build --no-cache
docker-compose --env-file .env.production.local up
```

#### 🔺 **Vercel**

Deploying this application to Vercel is quite simple. Follow the steps below and you should have a production build running on Vercel in just a few minutes.

  1. Fork or clone this repo to have it in your own Github account;
  2. Access the [Vercel login area](https://vercel.com/login) to log into it with your Github account;
  3. Select the _New Project_ option;
  4. Import the desired Git Repository;
  5. Select your personal account or team;
  6. Deploy! 🥳

---

To access the live preview, you can go to the [Vercel's production deployment](https://jungle-devs-react-challenge.vercel.app).
