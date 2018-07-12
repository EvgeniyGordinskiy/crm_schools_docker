FROM centos:latest
RUN groupadd -g 48 apache && useradd -d /home/apache -u 48 -g 48 apache
RUN yum -y update && yum -y install epel-release && yum -y install https://mirror.webtatic.com/yum/el7/webtatic-release.rpm \
	&& yum -y install yum-utils && yum makecache
RUN yum -y install php70w php70w-{bcmath,cli,common,devel,fpm,gd,interbase,intl,mbstring,mcrypt,mysqlnd,opcache,pear,pdo,process,soap,tidy,xml} php70w-pecl-{mongodb,redis} libpng-devel
RUN yum -y groupinstall  "Development Tools"
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=bin && mv /usr/bin/composer.phar /usr/bin/composer && chmod +x /usr/bin/composer
## Install nodejs ##

ADD runall.sh /opt/runall.sh

WORKDIR /data/crm_schools/httpdocs
RUN chmod 744 /opt/runall.sh

ENTRYPOINT ["/opt/runall.sh"]
#CMD ["env"]
