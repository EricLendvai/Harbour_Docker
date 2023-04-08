# Harbour Docker

The following repo is used to build images sent to Docker Hub.   

See the [docker documentation](https://docs.docker.com/engine/reference/commandline/build/).

## docker build
From the Docker folder inside the repo root folder execute the following to build images locally:   
To not use cached builds, remove "--no-cache"   
Call "docker build" with multiple tags to create a Docker image and tag as "latest" an a date.   

    docker build . -f Dockerfile_harbour_basic -t ericlendvai/harbour_basic:latest -t ericlendvai/harbour_basic:2023_04_07_003 --no-cache   

    docker build . -f Dockerfile_harbour_curl_hb-orm_hb-vfp_hb-fastcgi_apache_odbc-postgresql -t ericlendvai/harbour_curl_hb-orm_hb-vfp_hb-fastcgi_apache_odbc-postgresql:latest -t ericlendvai/harbour_curl_hb-orm_hb-vfp_hb-fastcgi_apache_odbc-postgresql:2023_04_07_003 --no-cache   

    docker build . -f Dockerfile_harbour_curl_hb-orm_hb-vfp_odbc-postgresql -t ericlendvai/harbour_curl_hb-orm_hb-vfp_odbc-postgresql:latest -t ericlendvai/harbour_curl_hb-orm_hb-vfp_odbc-postgresql:2023_04_07_003 --no-cache   

## docker push - Info only provided to help you setup and maintain your own docker hub repos

Login to your docker hub account.   
    docker login -u=DockerID -p=DockerPassword   

From the repo root folder execute the following to send to Docker Hub the new images. The tag "latest" will replace previous version".   
Call multiple "docker push".   
Don't use "--all-tags" option the since even existing images will be redates as current.   
    docker push ericlendvai/harbour_basic:2023_04_07_003
    docker push ericlendvai/harbour_basic:latest

    docker push ericlendvai/harbour_curl_hb-orm_hb-vfp_hb-fastcgi_apache_odbc-postgresql:2023_04_07_003
    docker push ericlendvai/harbour_curl_hb-orm_hb-vfp_hb-fastcgi_apache_odbc-postgresql:latest

    docker push ericlendvai/harbour_curl_hb-orm_hb-vfp_odbc-postgresql:2023_04_07_003
    docker push ericlendvai/harbour_curl_hb-orm_hb-vfp_odbc-postgresql:latest

