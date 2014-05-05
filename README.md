IMPORTANT
=========
For development servers - you need to comment the capybara gem

This is a good working copy of the service hosted on cloud compute server on vexxhost
Cloud66 had to fix something on their side for this to be deployed correctly.
This copy is also pushed to github at https://github.com/darpanp/copycopter-sql.git

check for git remote -v


Copycopter
==========

[![Build Status](https://secure.travis-ci.org/copycopter/copycopter-server.png)](http://travis-ci.org/copycopter/copycopter-server)

Copycopter is a service for editing the copy text of a Rails application.

Each Rails application has its own Project, connected by an API key.
Each piece of copy in a Project is a Blurb. Each Blurb has many Versions, which
track changes users make to copy.

Each Version is either draft or published. The most typical scenario is to
display published content in production, and draft in all other environments.

A developer can issue a deploy, which marks the latest Version of all Blurbs as
published.

Setup
-----

    git clone git://github.com/copycopter/copycopter-server.git
    cd copycopter-server

Deploy
------

Deploy Copycopter Server like any other Rails app. Heroku example:

    heroku create --stack cedar
    git push heroku master
    heroku run rake db:migrate
    heroku restart
    heroku run rake copycopter:project NAME=Iora USERNAME=Copy PASSWORD=Copter

Contribute
----------

See the [style guide](https://github.com/copycopter/style-guide).

Set up dependencies:

    bundle

Run the test suite:

    bundle exec rake

Run the server:

    foreman start

Automatically regenerate CSS when you edit Sass files:

    sass --watch public/stylesheets/sass:public/stylesheets \
      -r ./public/stylesheets/sass/bourbon/lib/bourbon.rb

Credits
-------

![thoughtbot](http://thoughtbot.com/images/tm/logo.png)

Copycopter Server was created by [thoughtbot, inc](http://thoughtbot.com)

It is maintained by the fine folks at [Crowdtap](http://crowdtap.com) and
[Iora Health](http://iorahealth.com).

License
-------

Copycopter Server is free software, and may be redistributed under the terms
specified in the MIT-LICENSE file.
