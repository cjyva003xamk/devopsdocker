# Start from the alpine image that is smaller but no fancy tools
FROM node:16-alpine as build-stage

WORKDIR /usr/src/app

COPY ./simpleserver .

RUN npm install

#after building-stage we move on to production-stage

FROM node:16-alpine

EXPOSE 3001

WORKDIR /usr/src/app

COPY --from=build-stage /usr/src/app /usr/src/app

RUN adduser -D appuser

USER appuser

CMD ["npm", "start"]