FROM debian
MAINTAINER DriouTech <admin@driou.tech>
ENV MARIADB_USER dbuser
ENV MARIADB_PASSWORD dbpassword
ENV MARIADB_DATABASE db
RUN apt-get update && apt-get install -y wget unzip python-software-properties software-properties-common
RUN apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 0xcbcb082a1bb943db
RUN add-apt-repository 'deb http://mirror6.layerjet.com/mariadb/repo/10.1/debian jessie main'
RUN apt-get update
RUN apt-cache search galera
RUN cat /etc/apt/sources.list
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y rsync mariadb-server galera-3
ADD my.cnf /etc/mysql/my.cnf
EXPOSE 3306 4444 4567 4568 4568/udp 
ADD mysql.sh /mysql.sh
RUN chmod +x /mysql.sh
RUN "./mysql.sh"
ADD entrypoint.sh /
RUN chmod +x /entrypoint.sh
CMD ["/entrypoint.sh"]
##
