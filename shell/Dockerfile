FROM centos:latest
RUN yum -y update && yum -y install epel-release && yum -y install https://mirror.webtatic.com/yum/el7/webtatic-release.rpm \
	&& yum -y install yum-utils && yum makecache
RUN yum -y install php70w php70w-{bcmath,cli,common,devel,fpm,gd,interbase,intl,mbstring,mcrypt,mysqlnd,opcache,pear,pdo,process,soap,tidy,xml} php70w-pecl-{mongodb,redis} mariadb
## Install Composer ##
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=bin && mv /usr/bin/composer.phar /usr/bin/composer && chmod +x /usr/bin/composer
## Install nodejs ##
RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - && yum -y install nodejs
RUN npm install -g @angular/cli
ADD ./shell.sh /usr/local/bin/shell.sh
RUN chmod 777 /usr/local/bin/shell.sh

WORKDIR /data/crm_schools/

CMD /usr/local/bin/shell.sh
