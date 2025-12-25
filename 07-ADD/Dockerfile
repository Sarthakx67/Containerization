# almalinux is same as centos
FROM almalinux:8
RUN yum install nginx -y
# Add works same as copy and can get files from internet example
ADD https://raw.githubusercontent.com/Sarthakx67/Containerization/refs/heads/main/06-COPY/portfolio.html /usr/share/nginx/html/
CMD ["nginx","-g","daemon off;"]