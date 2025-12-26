# ARG is used to define build-time variables (available only during `docker build`).
# You can pass it with: `docker build --build-arg version=9 .`
ARG version

# Use the build arg in the base image tag; default to 8 if not provided.
FROM almalinux:${version:-8}

# NOTE: ARGs declared *before* FROM are not automatically available after FROM
# unless re-declared. Add `ARG version` again below if you need it in later stages.
WORKDIR /tmp

# This will print the version *only if* `ARG version` is in scope here.
RUN echo "almalinux version is ${version}"


#----------------------------------BUILD COMMAND--------------------------------------

# docker build -t <image-name>:<version> --build-arg version=8