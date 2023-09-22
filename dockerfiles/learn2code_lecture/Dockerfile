FROM benniwi/learn2code:base_marp

RUN \
    sudo apt-get update \
    # install opencv
    && sudo apt-get install -y libopencv-dev \
    # install basics for armadillo
    && sudo apt-get install -y libopenblas-dev liblapack-dev libarpack2-dev libsuperlu-dev\
    # clean up
    && sudo rm -rf /var/lib/apt/lists/*

