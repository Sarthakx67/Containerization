# almalinux is same as centos
FROM almalinux:8
RUN yum install nginx -y
RUN echo "Hello From Sarthak" > /usr/share/nginx/html/hello.html
LABEL name=ROBOSHOP \
      ami=almalinux 
ENV NAME=Sarthak \
    AGE=30 \
    ADDRESS=India
COPY /d/Git-Repo/Containerization/06-COPY /usr/share/nginx/html/
CMD ["nginx","-g","daemon off;"]