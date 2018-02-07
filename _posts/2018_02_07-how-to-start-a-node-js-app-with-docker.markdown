---
layout: post
title:  "How to start a Node.js app with Docker"
date:   2018-02-07 07:37:40 +0100
categories: docker, node, js
---
Docker is a great way to abstract the OS-level, which is the requirement for auto-deployment to virtual compouters, such as EC2. This `Dockerfile` launches a Node.js environment.

## Step 1: Create a Node.js package

```
npm init
```

Add your code to e.g. `index.js` and add a start script to `package.json`:

```
{
  ...
  "scripts": {
    "start": "node index.js"
  },
  ...
}
```

## Step 2

```
FROM node:8
COPY package*.json ./
RUN npm install
COPY . .
CMD [ "npm", "start" ]
```

## Step 3: Add a `.dockerignore` file

```
node_modules
npm-debug.log
```

**Resources:**

* [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
