# almalinux is same as centos
FROM almalinux:8

RUN yum install -y nginx && yum clean all

# Add works same as copy and can get files from internet example
ADD https://raw.githubusercontent.com/Sarthakx67/Containerization/refs/heads/main/06-COPY/portfolio.html /usr/share/nginx/html/portfolio.html

# ensure nginx can read it
RUN chmod 644 /usr/share/nginx/html/portfolio.html

CMD ["nginx","-g","daemon off;"]