# ARG is used to define build-time variables (available only during `docker build`).
# You can pass it with: `docker build --build-arg version=9 .`
ARG version

# Use the build arg in the base image tag; -8 makes default to 8 if not provided.
FROM almalinux:${version:-8}

# NOTE:
# - `ARG version` was used in the FROM line above.
# - After `FROM`, that earlier ARG is NOT automatically in scope unless re-declared.
#   (So `${version}` in later RUN commands would be empty unless you add `ARG version` again.)

ARG NAME
ARG AGE

# Turn build-time ARG values into ENV vars baked into the image.
# What happens:
# - If you pass `--build-arg NAME=Alice --build-arg AGE=30` during build:
#     ENV NAME=Alice and ENV AGE=30 are stored in the image.
# - At runtime (`docker run`), containers start with these ENV defaults already set.
# - You can override them at runtime with `docker run -e NAME=Bob -e AGE=40 ...`.
ENV NAME=${NAME}
ENV AGE=${AGE}

# This runs at IMAGE BUILD TIME, not at container runtime.
# It prints the values that were provided via --build-arg during the build.
RUN echo "almalinux owner is ${NAME} of age ${AGE}"

#----------------------------------BUILD COMMAND--------------------------------------
# Build with args (bakes ENV defaults into the image):
#   docker build -t myimg:8 --build-arg version=8 --build-arg NAME=Alice --build-arg AGE=30 .
#
# If you do NOT pass NAME/AGE:
# - NAME and AGE will be empty, so ENV NAME= and ENV AGE= will be baked into the image.
#
# Run (uses baked-in ENV defaults):
#   docker run --rm myimg:8 env
#
# Run overriding at runtime (does NOT require rebuild):
#   docker run --rm -e NAME=Bob -e AGE=40 myimg:8 env