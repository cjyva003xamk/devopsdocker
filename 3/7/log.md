Before > docker system df -v
Images space usage:

REPOSITORY   TAG       IMAGE ID       CREATED              SIZE      SHARED SIZE   UNIQUE SIZE   CONTAINERS
frontti36    latest    50cda616ba5b   About a minute ago   1.26GB    0B            1.261GB       1
bakki36      latest    0c731fcaa601   12 minutes ago       1.07GB    0B            1.066GB       1

After changing images Alpine based:

Images space usage:

REPOSITORY   TAG       IMAGE ID       CREATED          SIZE      SHARED SIZE   UNIQUE SIZE   CONTAINERS
frontti37    latest    233ce55be800   2 minutes ago    470MB     0B            469.8MB       1
bakki37      latest    d19c1077a032   12 minutes ago   447MB     0B            447.4MB       
