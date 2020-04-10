FROM codercom/code-server:3.1.0

## Setup Java 8 Development Environment
# RUN sudo apt update \
#   && sudo apt install -y openjdk-8-jdk maven \
#   && sudo apt-get clean

RUN sudo apt update \
  && sudo apt -y upgrade \
  && sudo apt install -y apt-transport-https ca-certificates wget dirmngr gnupg software-properties-common \
  && wget -qO - https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public | sudo apt-key add - \
  && sudo add-apt-repository --yes https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/ \
  && sudo apt update \
  && sudo apt -y install adoptopenjdk-8-hotspot \
  && sudo apt-get clean

## Setup NodeJS 8 Development Environment
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
RUN sudo apt-get install -y nodejs

## Setup Angular
RUN sudo npm install -g @angular/cli

RUN code-server \
  --install-extension redhat.java \
  --install-extension vscjava.vscode-java-debug \
  --install-extension vscjava.vscode-java-test \
  --install-extension vscjava.vscode-maven \
  --install-extension vscjava.vscode-java-dependency \
  # --install-extension Pivotal.vscode-spring-boot \
  --install-extension vscjava.vscode-spring-initializr \
  --install-extension vscjava.vscode-spring-boot-dashboard \
  --install-extension dbaeumer.vscode-eslint \
  --install-extension eg2.vscode-npm-script \
  --install-extension xabikos.JavaScriptSnippets \
  --install-extension jasonnutter.search-node-modules \
  --install-extension christian-kohler.path-intellisense
