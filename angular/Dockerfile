FROM node:8

ADD ./runall.sh /opt/runall.sh
WORKDIR /data/crm_schools/httpdocs_angular
RUN chmod 744 /opt/runall.sh

ENTRYPOINT ["/opt/runall.sh"]

