FROM almalinux:8
RUN yum install -y nginx && yum clean all

# ENTRYPOINT sets the container’s main executable; here it always starts nginx in the foreground 
# so the container stays running.
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]