# gitlab-ce with docker-compose
[![Build Status](https://files.ariadata.co/file/ariadata_logo.png)](https://ariadata.co)

![](https://img.shields.io/github/stars/ariadata/dc-gitlab.svg)
![](https://img.shields.io/github/watchers/ariadata/dc-gitlab.svg)
![](https://img.shields.io/github/forks/ariadata/dc-gitlab.svg)

> This needs : [nginx-proxy-manager with docker-compose](https://github.com/ariadata/dc-nginxproxymanager) .

---
#### 1- Clone these repository to your system :
```sh
git clone https://github.com/ariadata/dc-gitlab.git
```
#### 2- cd into created folder :
```sh
cd dc-gitlab
```
#### 3- edit `docker-compose.yml` ( lines : 7,10 ):
#### 4- Run docker-compose file by using :
```sh
docker-compose up -d
```
#### 3- Goto Nginx-Proxy-Manager admin panel and add this stack as proxy-host :
> Domain : `Your-FQDN` you must point it before!
> 
> Schema : `https`
> 
> Name or IP : `gitlab`
> 
> Port : `443`
>
> Config SSL Certificate is

#### 5- Goto gitlab setup page : 
>  `https://Your-FQDN/`
>  

Done!


