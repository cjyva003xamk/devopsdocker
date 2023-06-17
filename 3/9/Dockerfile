# Start from the alpine image that is smaller but no fancy tools
FROM golang:1.16-alpine as build-stage

WORKDIR /usr/src/app

COPY . .

RUN  CGO_ENABLED=0 go build && adduser -D backenduser 
 
FROM scratch

COPY --from=build-stage /etc/passwd /etc/passwd

COPY --from=build-stage /usr/src/app /usr/src/app

EXPOSE 8080

ENV REQUEST_ORIGIN=http://localhost:5000

USER backenduser

#CMD ["./server"]

ENTRYPOINT ["/usr/src/app/server"]