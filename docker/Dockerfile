FROM ubuntu:18.04
ENV os=ubuntu:18.04
ENV TERM=xterm
ENV maintainer "Egidijus Ligeika"
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get dist-upgrade -qy && \
    apt-get install -yq \
    gcc libc6-dev make curl automake \
    bash-completion \
    python3 python3-setuptools python3-dev \
    libxml2-utils \
    locales \
    lsb-release \
    build-essential \
    python python-setuptools python-dev \
    nvidia-cuda-dev python3-pycuda python-pycuda \
    cmake sudo libboost-tools-dev magics++\
    vim mlocate apt-utils \
    liblld-6.0-dev llvm-6.0-dev \
    git
RUN echo "source /etc/profile.d/bash_completion.sh" >> ~/.bashrc

ADD blender-src /blender-src
WORKDIR /blender-src
RUN ./build_files/build_environment/install_deps.sh --show-deps && \
    ./build_files/build_environment/install_deps.sh --with-all --no-confirm --force-boost --force-python --build-llvm --build-osl --force-osl
RUN make full

ENTRYPOINT watch ls /