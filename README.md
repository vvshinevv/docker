# docker


1번

 - 192.168.56.107

2번

 - 192.168.56.108

3번

 

https://docs.docker.com/

 

iptraf-ng

docker-stats

cadvisor

 

 

이미지 설명

 - container는 불변

 - docker (container) run

 - registry

  - 저장소를 설명

 

 - tar : 묶음? 

  - 왜 tar를? - layer때문에

  - 계층을 묶어야해서?

  - tar gz

 

 - image : 정적

 - container : 동적

 

 - container 수정 => commit => push => backup

 

 - kill : kill -l 프로세스에게 신호를 보낸다

   - kill -9 프로세스를 죽여라

 - container에서는 세션을 죽인다?

 

sudo iptraf-ng

centos : comunity enterprize...

 

docker pull (docker.io)centos:7

docker pull gcr.io/google-samples/hello-app:1.0

주소 / 레포 / 이미지 : 버전

 

 

[p96]

docker image history httpd:2.4

 

 

docker container 실체

 - process다?

 - local volume(disk)

 

 

 

digest 이미지를 보호하기 위해서 ... 암호화가 필요업어서 hash만적용

 

 

 

 

 

 

docker image 모두 삭제

 - 불필요한 image / container 많이 쌓는다.

 - docker ps -a -q

 - docker stop $(docker ps -q)

 - alias cexrm='docker rm $(docker ps --filter 'status=exited' -a -q)'

 

 

 

login logout

jeff@jeff-VirtualBox:~$ cat /home/jeff/.docker/config.json

{

        "auths": {

                "https://index.docker.io/v1/": {

                        "auth": "dnZzaGluZXZ2OnkxMjcxMDM5Mzk2Kg=="

                }

        },

        "HttpHeaders": {

                "User-Agent": "Docker-Client/18.09.3 (linux)"

        }

}

 

 

events {

        worker_connections 1024;

}

 

http {

        upstream nginx-lb {

                server 127.0.0.1:5001;

                server 127.0.0.1:5002;

                server 127.0.0.1:5003;

        }

 

        server {

                listen 80 default_server;

                listen [::]:80 default_server;

 

                location / {

                        proxy_pass      http://nginx-lb;

                }

        }

}

 

 

brctl show

 - 도커에 붙은 컨터에너들을 알 수 있다.
