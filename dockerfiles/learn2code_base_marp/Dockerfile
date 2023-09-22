FROM benniwi/learn2code:base

RUN \
    sudo apt-get update \
    && sudo apt-get install -y wget \
    # install google chrome
    && sudo apt-get install -y fonts-liberation libasound2 libatk-bridge2.0-0 libatk1.0-0 libatspi2.0-0 libcairo2 libcups2\
    libdrm2 libgbm1 libgtk-3-0 libnspr4 libnss3 libpango-1.0-0 libu2f-udev libvulkan1 libxss1 libx11-6 libxcb1 libxcomposite1\
    libxdamage1 libxext6 libxfixes3 libxkbcommon0 libxrandr2 xdg-utils \
    && sudo wget -q https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
    && sudo dpkg -i google-chrome-stable_current_amd64.deb \
    && sudo rm ./google-chrome-stable_current_amd64.deb \ 
    # install latest nodejs
    && sudo apt-get install -y ca-certificates curl gnupg \
    && sudo curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/nodesource.gpg \
    && NODE_MAJOR=20 \
    && echo "deb [signed-by=/etc/apt/trusted.gpg.d/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo  tee /etc/apt/sources.list.d/nodesource.list \
    && sudo apt-get update \
    && sudo apt-get install -y nodejs \
    && sudo npm install -g @marp-team/marp-cli \
    # clean up
    && sudo rm -rf /var/lib/apt/lists/*

