FROM benniwi/learn2code:24.04_base

RUN \
    sudo apt-get update \
    && sudo apt-get install -y wget \
    # install google chrome
    && sudo wget -q https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
    && sudo apt-get install -y ./google-chrome-stable_current_amd64.deb \
    # install latest nodejs
    && sudo apt-get install -y ca-certificates curl gnupg \
    && sudo curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/nodesource.gpg \
    && NODE_MAJOR=22 \
    && echo "deb [signed-by=/etc/apt/trusted.gpg.d/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo  tee /etc/apt/sources.list.d/nodesource.list \
    && sudo apt-get update \
    && sudo apt-get install -y nodejs \
    && sudo npm install -g @marp-team/marp-cli \
    # clean up
    && sudo rm -rf /var/lib/apt/lists/*

