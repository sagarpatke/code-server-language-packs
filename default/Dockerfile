FROM codercom/code-server

## Setup Java 8 Development Environment
RUN sudo apt update && sudo apt install -y openjdk-8-jdk maven && sudo apt-get clean
RUN wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

RUN code-server \
  --install-extension redhat.java \
  --install-extension vscjava.vscode-java-debug \
  --install-extension vscjava.vscode-java-test \
  --install-extension vscjava.vscode-maven \
  --install-extension vscjava.vscode-java-dependency
RUN code-server \
  --install-extension Pivotal.vscode-spring-boot \
  --install-extension vscjava.vscode-spring-initializr \
  --install-extension vscjava.vscode-spring-boot-dashboard

## Setup NodeJS 8 Development Environment
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

RUN sudo apt install -y nodejs && sudo apt-get clean
RUN sudo npm install -g @angular/cli

RUN code-server \
  --install-extension dbaeumer.vscode-eslint \
  --install-extension eg2.vscode-npm-script \
  --install-extension xabikos.JavaScriptSnippets \
  --install-extension jasonnutter.search-node-modules \
  --install-extension christian-kohler.path-intellisense
