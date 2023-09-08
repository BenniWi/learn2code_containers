FROM ubuntu:20.

# fix the timezone asking when creating the container
ENV TZ=Europe/Berlin
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN \
 apt-get -y update \
 && apt-get install -y git build-essential lldb gdb ninja-build libgtest-dev wget curl software-properties-common \
 # bring in latest cmake
 && wget -qO /etc/apt/trusted.gpg.d/kitware-key.asc https://apt.kitware.com/keys/kitware-archive-latest.asc \ 
 && echo "deb https://apt.kitware.com/ubuntu/ focal main" | tee /etc/apt/sources.list.d/kitware.list \
 && add-apt-repository -y ppa:system76/pop \
 && apt-get update \
 && apt-get install -y cmake \
  # bring in latest clang toolchain
 && wget https://apt.llvm.org/llvm.sh \
 && chmod +x llvm.sh \
 && ./llvm.sh 16 all \
 && rm llvm.sh \
# clean up
 && rm -rf /var/lib/apt/lists/*
