# Start from the alpine image that is smaller but no fancy tools
FROM node:16-alpine as build-stage

#ENV REACT_APP_BACKEND_URL=http://localhost:8080

 WORKDIR /usr/src/app

 COPY . .



RUN npm install && npm run build

#after building-stage we move on to production-stage

FROM node:16-alpine

EXPOSE 5000

WORKDIR /usr/src/app

COPY --from=build-stage /usr/src/app/build /usr/src/app/build

RUN npm install -g serve && adduser -D frontenduser

USER frontenduser

CMD ["serve", "-s", "-l", "5000", "build"]