# almalinux is same as centos
FROM almalinux:8
RUN yum install nginx -y
RUN echo "Hello From Sarthak" > /usr/share/nginx/html/hello.html
CMD ["nginx","-g","daemon off;"]