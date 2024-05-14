FROM node:20.13.0-alpine3.19 AS development

WORKDIR /usr/src/app

COPY --chown=node:node package.json package-lock.json ./

RUN npm install

COPY --chown=node:node . .

USER node

FROM node:20.13.0-alpine3.19 AS build

WORKDIR /usr/src/app

COPY --chown=node:node --from=development /usr/src/app/package.json /usr/src/app/package-lock.json ./

RUN npm install --frozen-lockfile --production=true

COPY --chown=node:node . .

COPY .env .env

RUN npm run build

ENV NODE_ENV production

USER node

FROM node:20.13.0-alpine3.19 AS production

COPY --chown=node:node --from=build /usr/src/app .

CMD [ "npm", "run","start:prod" ]