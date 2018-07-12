FROM centos:latest
RUN yum -y update && yum -y install epel-release && yum -y install https://mirror.webtatic.com/yum/el7/webtatic-release.rpm \
	&& yum -y install yum-utils && yum makecache
RUN yum -y install php70w php70w-{bcmath,cli,common,devel,fpm,gd,interbase,intl,mbstring,mcrypt,mysqlnd,opcache,pear,pdo,process,soap,tidy,xml} php70w-pecl-{mongodb,redis}
ADD pool.conf /etc/php-fpm.d/www.conf

EXPOSE 9000

ENTRYPOINT ["/usr/sbin/php-fpm", "-F"]
