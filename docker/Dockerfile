FROM node:16.17.1-alpine3.16 as build

WORKDIR /usr/src/app

COPY . .

RUN yarn install && \
    yarn build 

FROM oap75/nginx:1.1.2

COPY --from=build /usr/src/app/build /usr/share/nginx/html
