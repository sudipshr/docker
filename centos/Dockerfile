FROM centos:latest 
RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install httpd && \
    yum clean all

# Install apache and write hello world message
RUN echo "Hello World from Centos!" > /var/www/index.html

# Configure apache
ENV APACHE_LOG_DIR /var/log/apache2

EXPOSE 80

# Simple startup script to avoid some issues observed with container restart
ADD run-httpd.sh /run-httpd.sh
RUN chmod -v +x /run-httpd.sh

CMD ["/run-httpd.sh"]
