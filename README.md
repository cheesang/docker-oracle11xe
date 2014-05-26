Docker to installs Oracle 11g XE, SSHD & Supervisord
====================================================

Thanks to Maciej Próchniak (https://github.com/mproch/docker-oracle-xe), I have modified his docker file which install Oracle 11g XE with SSH feature and the services will autostart using Supervisor.


**Steps:**

1. please download Oracle 11g XE from http://www.oracle.com/technetwork/database/database-technologies/express-edition/downloads/index.html
2. extract RPM file from the zip downloaded into  \files


**to run the docker image**

> docker run -d -p  ??:1521 -p  ??:22 -p  ??:8080

*replace ?? with port required*

**Password**

ssh login = root/root, to change please modified this line in dockerfile
> RUN echo 'root:root' |chpasswd

<br/>
oracle password for sys and system is 'oracle', to change please modified this line in install.sh

> /usr/bin/printf 8080\\n1521\\n<b>oracle</b>\\n<b>oracle</b>\\ny\\n | /etc/init.d/oracle-xe configure
