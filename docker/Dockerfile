FROM ubuntu:18.04
ENV os=ubuntu:18.04
ENV TERM=xterm
ENV maintainer "Egidijus Ligeika"
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -yq \
    gcc libc6-dev make curl python3 \
    python3-setuptools \
    libxml2-utils \
    locales \
    lsb-release \
    build-essential \
    cmake sudo \
    vim \
    git


ADD blender-src /blender-src
WORKDIR /blender-src
RUN ./build_files/build_environment/install_deps.sh --show-deps && \
    ./build_files/build_environment/install_deps.sh --with-all --no-confirm


ENTRYPOINT watch ls /