FROM codercom/code-server

## Setup Java 8 Development Environment
RUN sudo apt update \
  && sudo apt install -y openjdk-8-jdk maven \
  && sudo apt-get clean

## Setup NodeJS 8 Development Environment
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
RUN sudo apt-get install -y nodejs

## Setup Angular
RUN sudo npm install -g @angular/cli && sudo chown 1000:1000 -R /home/coder/.config

RUN code-server \
  --install-extension redhat.java \
  --install-extension vscjava.vscode-java-debug \
  --install-extension vscjava.vscode-java-test \
#  --install-extension vscjava.vscode-maven \
  --install-extension vscjava.vscode-java-dependency \
#  --install-extension pivotal.vscode-spring-boot \
  --install-extension vscjava.vscode-spring-initializr \
  --install-extension vscjava.vscode-spring-boot-dashboard \
  --install-extension dbaeumer.vscode-eslint \
  --install-extension eg2.vscode-npm-script \
  --install-extension xabikos.JavaScriptSnippets \
  --install-extension jasonnutter.search-node-modules \
  --install-extension christian-kohler.path-intellisense
