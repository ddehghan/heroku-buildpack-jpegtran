Heroku Buildpack: jpegtran
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [jpegtran](http://jpegclub.org/jpegtran/) in your application.  

It is designed to be used with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with the appropriate real buildpack for your app.

This is based on https://github.com/jayzes/heroku-buildpack-optipng.

Usage
-----
Add a `.buildpacks` file to the root of your repo that contains this buildpack URL and your real buildpack URL:

    https://github.com/aeby/heroku-buildpack-jpegtran
    https://github.com/heroku/heroku-buildpack-python

Then create an application using the multi buildpack:

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

or configure an existing application:

    $ heroku buildpacks:set https://github.com/ddollar/heroku-buildpack-multi.git

You can verify that everything is properly installed by running the following command:

    $ heroku run "jpegtran -v"
