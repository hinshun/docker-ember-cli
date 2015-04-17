FROM node:0.12

# add our user and group first to make sure their IDs get assigned consistently, regardless of whatever dependencies get added
RUN groupadd -r ember-cli && useradd -r -g ember-cli ember-cli

ENV EMBER_CLI_VERSION=0.2.3

RUN npm install -g ember-cli@$EMBER_CLI_VERSION bower phantomjs

EXPOSE 4200 35729

CMD [ "ember" ]
