FROM hinshun/ember-cli:0.2.6

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY package.json /usr/src/app/
ONBUILD COPY bower.json /usr/src/app/
ONBUILD RUN npm install && bower install --allow-root

ONBUILD COPY . /usr/src/app

CMD [ "ember", "server" ]
