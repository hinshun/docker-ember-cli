# Supported tags and respective `Dockerfile` links

-	[`0.2.7`, `latest` (*0.2.7/Dockerfile*)](https://github.com/hinshun/docker-ember-cli/blob/aa3cc7383f3e67c2304dac0e6d8035b94988be9e/0.2.7/Dockerfile)
-	[`0.2.7-onbuild`, `onbuild` (*0.2.7/onbuild/Dockerfile*)](https://github.com/hinshun/docker-ember-cli/blob/aa3cc7383f3e67c2304dac0e6d8035b94988be9e/0.2.7/onbuild/Dockerfile)

# What is Ember CLI?

Ember CLI is an Ember.js command line utility which provides a fast asset pipeline powered by Broccoli and strong conventional project structure.

> [ember-cli.com](http://www.ember-cli.com/#overview)

![logo](http://emberjs.com/images/logos/ember-logo.png)

# How to use this image

## Create a `Dockerfile` in your Ember app project

	FROM hinshun/ember-cli:0.2.7-onbuild

Put this file in the root of your app.

This image includes multiple `ONBUILD` triggers which should be all you need to bootstrap most applications. The build will `COPY package.json /usr/src/app`, `COPY bower.json /usr/src/app` and `RUN npm install && bower install --allow-root`.

You can then build and run the Ember image:

	docker build -t my-ember-app .
	docker run my-ember-app

### Generate an Ember app

The `onbuild` tag expects a `package.json` and `bower.json` in your app directory. This `docker run` will help you generate one. Run it in the root of your app:

	docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app hinshun/ember-cli:0.2.7 cd /usr/src/app && ember new my-ember-app 

# License

View [license information](https://github.com/ember-cli/ember-cli/blob/master/LICENSE.md) for the software contained in this image.

# Supported Docker versions

This image is officially supported on Docker version 1.7.0.

Support for older versions (down to 1.0) is provided on a best-effort basis.

# User Feedback

## Documentation

Documentation for this image is stored in the [`docker-ember-cli` GitHub repo](https://github.com/hinshun/docker-ember-cli).

## Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/hinshun/docker-ember-cli/issues).
