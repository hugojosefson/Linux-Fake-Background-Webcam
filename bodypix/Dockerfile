FROM node:16-buster-slim AS build

WORKDIR /src

COPY package.json /src/

RUN apt-get update && \
    apt-get install --no-install-recommends -y build-essential python3 python3-dev && \
    yarn install

FROM node:16-buster-slim

COPY --from=build /src /src

WORKDIR /src

COPY app.js /src/

ENTRYPOINT node /src/app.js
