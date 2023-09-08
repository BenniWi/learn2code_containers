FROM benniwi:learn2code:base

RUN \
 apt-get update \
# install google chrome
 &&  apt-get install -y fonts-liberation libasound2 libatk-bridge2.0-0 libatk1.0-0 libatspi2.0-0 libcairo2 libcups2\
 libdrm2 libgbm1 libgtk-3-0 libnspr4 libnss3 libpango-1.0-0 libu2f-udev libvulkan1 libx11-6 libxcb1 libxcomposite1\
 libxdamage1 libxext6 libxfixes3 libxkbcommon0 libxrandr2 xdg-utils \
 && wget -q https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
 && dpkg -i google-chrome-stable_current_amd64.deb \
 && rm ./google-chrome-stable_current_amd64.deb \ 
# install latest nodejs
 && apt install -y curl \
 && curl -sL https://deb.nodesource.com/setup_18.x | bash - \
 && apt-get update \
 && apt-get install -y nodejs \
 && npm install -g @marp-team/marp-cli \
# install opencv
 && apt-get install -y libopencv-dev \
# install basics for armadillo
 && apt-get install -y libopenblas-dev liblapack-dev libarpack2-dev libsuperlu-dev\
# clean up
 && rm -rf /var/lib/apt/lists/*
