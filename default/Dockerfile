FROM codercom/code-server:3.4.1

RUN sudo apt update \
  && sudo apt -y upgrade \
  && sudo apt install -y apt-transport-https ca-certificates wget dirmngr gnupg software-properties-common openjdk-11-jdk maven \
  && sudo apt-get clean

## Setup NodeJS 12 Development Environment
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
RUN sudo apt-get install -y nodejs

## Setup Angular
RUN sudo npm install -g @angular/cli@8

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

RUN mkdir .ext
COPY codetour-0.0.32.vsix .ext
RUN code-server --install-extension .ext/codetour-0.0.32.vsix
RUN wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
RUN echo deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main | sudo tee /etc/apt/sources.list.d/google-chrome.list
RUN sudo apt-get update && sudo apt-get -y install google-chrome-stable
