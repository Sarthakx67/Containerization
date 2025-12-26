FROM almalinux:8
RUN yum install -y nginx
RUN rm -rf /usr/share/nginx/html/

# ONBUILD makes rules that triggers run when a CHILD image is built FROM this image:
# - If the child build context contains index.html, it will be copied into nginx web root.
# - If the child does NOT have index.html, the child build will fail at this step.
ONBUILD ADD index.html /usr/share/nginx/html/


CMD [ "nginx" ,"-g", "daemon off;" ]