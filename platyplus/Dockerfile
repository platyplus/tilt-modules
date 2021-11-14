FROM node:16-alpine
ARG NODE_ENV=production
ENV NODE_ENV $NODE_ENV
RUN apk add --no-cache git vips

WORKDIR /app
ADD package.json .
ADD yarn.lock .
RUN --mount=type=cache,target=/root/.yarn YARN_CACHE_FOLDER=/root/.yarn yarn install

ADD . .
CMD ["yarn", "start"]