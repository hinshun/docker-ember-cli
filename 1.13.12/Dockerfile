FROM node:0.12

ENV EMBER_CLI_VERSION=1.13.12

RUN npm install -g ember-cli@$EMBER_CLI_VERSION bower phantomjs

RUN git clone https://github.com/facebook/watchman.git && \
  cd watchman && \
  git checkout v3.1 && \
  ./autogen.sh && \
  ./configure && \
  make && \
  make install

EXPOSE 4200 35729

CMD [ "ember" ]
