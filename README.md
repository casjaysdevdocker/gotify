## 👋 Welcome to gotify 🚀  

gotify README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update gotify
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/gotify/gotify/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/gotify/rootfs"
git clone "https://github.com/dockermgr/gotify" "$HOME/.local/share/CasjaysDev/dockermgr/gotify"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/gotify/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-gotify-latest \
--hostname gotify \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/gotify:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/gotify
    container_name: casjaysdevdocker-gotify
    environment:
      - TZ=America/New_York
      - HOSTNAME=gotify
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/gotify/gotify/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/gotify/gotify/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/gotify
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/gotify" "$HOME/Projects/github/casjaysdevdocker/gotify"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/gotify"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
