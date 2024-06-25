#specify the base image which can be pulled from a contain registry
FROM ubuntu:24.04

#executes commands during the image build process 
RUN apt-get update
RUN apt-get install -y nginx zip curl

RUN echo "daemon off;" >>/etc/nginx/nginx.conf
RUN curl -o /var/www/html/master.zip -L https://codeload.github.com/gabrielecirulli/2048/zip/master
RUN cd /var/www/html && unzip master.zip && mv 2048-master/* . && rm -rf 2048-master master.zip

#specifies the port to be exposed for the docker container
#80 http
EXPOSE 80

#start
CMD ["/usr/sbin/nginx", "-c", "/etc/nginx/nginx.conf"]

