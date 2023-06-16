before 

> docker image history frontti
IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
0fddd5bdd77d   20 minutes ago   CMD ["serve" "-s" "-l" "5000" "build"]          0B        buildkit.dockerfile.v0
<missing>      20 minutes ago   RUN /bin/sh -c useradd -m frontenduser # bui…   334kB     buildkit.dockerfile.v0
<missing>      2 hours ago      COPY . . # buildkit                             755kB     buildkit.dockerfile.v0
<missing>      2 hours ago      WORKDIR /usr/src/app                            0B        buildkit.dockerfile.v0
<missing>      2 hours ago      ENV REACT_APP_BACKEND_URL=http://localhost:8…   0B        buildkit.dockerfile.v0
<missing>      2 hours ago      EXPOSE map[5000/tcp:{}]                         0B        buildkit.dockerfile.v0
<missing>      2 days ago       /bin/sh -c #(nop)  CMD ["node"]                 0B
<missing>      2 days ago       /bin/sh -c #(nop)  ENTRYPOINT ["docker-entry…   0B
<missing>      2 days ago       /bin/sh -c #(nop) COPY file:4d192565a7220e13…   388B
<missing>      2 days ago       /bin/sh -c set -ex   && for key in     6A010…   7.59MB
<missing>      2 days ago       /bin/sh -c #(nop)  ENV YARN_VERSION=1.22.19     0B
<missing>      2 days ago       /bin/sh -c ARCH= && dpkgArch="$(dpkg --print…   98.5MB
<missing>      2 days ago       /bin/sh -c #(nop)  ENV NODE_VERSION=16.20.0     0B
<missing>      2 days ago       /bin/sh -c groupadd --gid 1000 node   && use…   334kB
<missing>      3 days ago       /bin/sh -c set -ex;  apt-get update;  apt-ge…   510MB
<missing>      3 days ago       /bin/sh -c apt-get update && apt-get install…   146MB
<missing>      3 days ago       /bin/sh -c set -eux;  apt-get update;  apt-g…   33MB
<missing>      3 days ago       /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      3 days ago       /bin/sh -c #(nop) ADD file:54838b3dbf7839dad…   114MB

> docker image history bakki  
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
4bcbaf0b675a   2 hours ago     CMD ["./server"]                                0B        buildkit.dockerfile.v0
<missing>      2 hours ago     USER backenduser                                0B        buildkit.dockerfile.v0
<missing>      2 hours ago     RUN /bin/sh -c adduser backenduser # buildkit   334kB     buildkit.dockerfile.v0
<missing>      2 hours ago     RUN /bin/sh -c go build # buildkit              146MB     buildkit.dockerfile.v0
<missing>      6 days ago      ENV REQUEST_ORIGIN=http://localhost:5000        0B        buildkit.dockerfile.v0
<missing>      6 days ago      COPY . . # buildkit                             28.9kB    buildkit.dockerfile.v0
<missing>      6 days ago      WORKDIR /usr/src/app                            0B        buildkit.dockerfile.v0
<missing>      6 days ago      EXPOSE map[8080/tcp:{}]                         0B        buildkit.dockerfile.v0
<missing>      15 months ago   /bin/sh -c #(nop) WORKDIR /go                   0B
<missing>      15 months ago   /bin/sh -c mkdir -p "$GOPATH/src" "$GOPATH/b…   0B
<missing>      15 months ago   /bin/sh -c #(nop)  ENV PATH=/go/bin:/usr/loc…   0B
<missing>      15 months ago   /bin/sh -c #(nop)  ENV GOPATH=/go               0B
<missing>      15 months ago   /bin/sh -c set -eux;  arch="$(dpkg --print-a…   387MB
<missing>      15 months ago   /bin/sh -c #(nop)  ENV GOLANG_VERSION=1.16.15   0B
<missing>      15 months ago   /bin/sh -c #(nop)  ENV PATH=/usr/local/go/bi…   0B
<missing>      15 months ago   /bin/sh -c set -eux;  apt-get update;  apt-g…   227MB
<missing>      15 months ago   /bin/sh -c apt-get update && apt-get install…   152MB
<missing>      15 months ago   /bin/sh -c set -ex;  if ! command -v gpg > /…   18.9MB
<missing>      15 months ago   /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      15 months ago   /bin/sh -c #(nop) ADD file:9c4db2a9644ee3029…   124MB


> docker system df -v
Images space usage:

REPOSITORY   TAG       IMAGE ID       CREATED          SIZE      SHARED SIZE   UNIQUE SIZE   CONTAINERS
frontti      latest    0fddd5bdd77d   27 minutes ago   1.26GB    0B            1.261GB       0
bakki        latest    4bcbaf0b675a   2 hours ago      1.07GB    0B            1.066GB       0

after combining RUN commands & removing unnecessary files

Images space usage:

REPOSITORY   TAG       IMAGE ID       CREATED              SIZE      SHARED SIZE   UNIQUE SIZE   CONTAINERS
frontti36    latest    50cda616ba5b   About a minute ago   1.26GB    0B            1.261GB       1
bakki36      latest    0c731fcaa601   12 minutes ago       1.07GB    0B            1.066GB       1