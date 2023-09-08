FROM ubuntu:20.04

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# fix the timezone asking when creating the container
ENV TZ=Europe/Berlin
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

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



#RUN \
#    echo 'export FMT_RESET="\e[0m"' >> /dev/.bash_profile \
#    echo 'export FG_BLACK="\e[30m"' >> /dev/.bash_profile \
#    echo 'export FG_GREEN="\e[32m"' >> /dev/.bash_profile \
#    echo 'export FG_MAGENTA="\e[35m"' >> /dev/.bash_profile \
#    echo 'export FG_RED="\e[31m"' >> /dev/.bash_profile \
#    echo 'export FG_WHITE="\e[97m"' >> /dev/.bash_profile \
#    echo 'export BG_BLUE="\e[44m"' >> /dev/.bash_profile \
#    echo 'export BG_GREEN="\e[42m"' >> /dev/.bash_profile \
#    echo 'export BG_MAGENTA="\e[45m"' >> /dev/.bash_profile \
#    echo 'export PS1="\n\[${BG_GREEN}\] \[${FG_RED}\]>> \[${FG_BLACK}\]\u \[${FG_GREEN}${BG_BLUE}\]\[${FG_BLACK}\]\w \[${FMT_RESET}${FG_BLUE}\]\[${BG_MAGENTA}\]\[${FG_WHITE}\]\$( git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/' )\[${FMT_RESET}${FG_MAGENTA}\]\n \[${FG_GREEN}\]╰ \[${FG_CYAN}\]\$ \[${FMT_RESET}\]"' >> /root/.bash_profile

USER $USERNAME

    
    
    
    
    
    
    
    
    


    
