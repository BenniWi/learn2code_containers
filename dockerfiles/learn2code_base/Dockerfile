FROM ubuntu:22.04

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID
ARG CMAKE_VERSION=3.27.7

# fix the timezone asking when creating the container
ENV TZ=Europe/Berlin
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# install everything we need
RUN \
    apt-get -y update \
    && apt-get install -y git build-essential lldb gdb ninja-build libgtest-dev wget curl software-properties-common libssl-dev\
    # bring in latest cmake - download it as binary
    && wget https://github.com/Kitware/CMake/releases/download/v$CMAKE_VERSION/cmake-$CMAKE_VERSION-linux-x86_64.sh \
    && chmod +x cmake-$CMAKE_VERSION-linux-x86_64.sh \
    && ./cmake-$CMAKE_VERSION-linux-x86_64.sh --skip-license \
    && rm cmake-$CMAKE_VERSION-linux-x86_64.sh \
    # bring in latest clang toolchain
    && wget https://apt.llvm.org/llvm.sh \
    && chmod +x llvm.sh \
    && ./llvm.sh 16 all \
    && rm llvm.sh \
    # clean up
    && rm -rf /var/lib/apt/lists/*

# bring in a nice shell prompt
COPY ./prompt.sh /home/dev/.prompt
RUN \
    chown dev:dev /home/dev/.prompt \
    && echo 'source /home/dev/.prompt' >> /home/dev/.bashrc
    
# set user to start and working directory
USER $USERNAME
WORKDIR /home/$USERNAME

    
    
    
    
    
    
    
    
    


    
