# gitlab-ce with docker-compose
[![Build Status](https://files.ariadata.co/file/ariadata_logo.png)](https://ariadata.co)

![](https://img.shields.io/github/stars/ariadata/dc-gitlab.svg)
![](https://img.shields.io/github/watchers/ariadata/dc-gitlab.svg)
![](https://img.shields.io/github/forks/ariadata/dc-gitlab.svg)

### This needs : [dockerhost](https://github.com/ariadata/dockerhost-sh) + [nginx-proxy-manager](https://github.com/ariadata/dc-nginxproxymanager)

---
#### 1- Change ssh port `via root user` (NOT 22) :
```sh
bash <(curl -Ls https://gist.github.com/pcmehrdad/2fbc9651a6cff249f0576b784fdadef0/raw)
```
---
#### 2- Login as `Normal User` and clone these repository to your system :
```sh
git clone https://github.com/ariadata/dc-gitlab.git && cd dc-gitlab && rm -rf .git
```
#### 3- edit `docker-compose.yml` ( lines : 7,10 ) according to your FQDN :
#### 4- Run docker-compose file by using :
```sh
docker-compose up -d
```
#### 5- set root login password for gitlab (** wait atleast 1 minute before these **):
```sh
docker exec -it gitlab bash
gitlab-rake "gitlab:password:reset[root]"
```
#### 6- (optional) change [gitlab smtp mail settings](https://docs.gitlab.com/omnibus/settings/smtp.html) , use these commands to save and check:
```sh
gitlab-ctl reconfigure
gitlab-rails console
Notify.test_email('you@example.com', 'Message Subject', 'Message Body').deliver_now
```
#### 7- Goto Nginx-Proxy-Manager admin panel and add this stack as proxy-host :
> Domain : `Your-FQDN` you must pointed it before!
> 
> Schema : `https`
> 
> Name or IP : `gitlab`
> 
> Port : `443`
>
> Config SSL Part

#### 9- goto : `https://Your-FQDN/`

Done!


