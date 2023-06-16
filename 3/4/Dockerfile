FROM docker

RUN  apk update && apk add git

COPY . .

ENTRYPOINT [ "sh", "/builder.sh" ]