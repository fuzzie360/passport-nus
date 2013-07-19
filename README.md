# Passport-NUS

[Passport](http://passportjs.org/) strategy for authenticating against NUS LDAP servers.

This module lets you authenticate against NUS LDAP servers in your Node.js applications.
By plugging into Passport, NUSNET authentication can be easily and
unobtrusively integrated into any application or framework that supports
[Connect](http://www.senchalabs.org/connect/)-style middleware, including
[Express](http://expressjs.com/).

## Install

    $ npm install passport-nus

## Usage

#### Configure Strategy

The NUS authentication strategy authenticates requests by delegating to the
nus ldap servers using the openldap protocol.

The strategy requires a `verify` callback which accepts a user `profile` entry
from the directory, and then calls the `done` callback supplying a `user`.

    passport.use(new NusStrategy(
      function(profile, done) {
        return done(null, JSON.parse(profile));
      }
    ));

#### Authenticate Requests

Use `passport.authenticate()`, specifying the `'nus'` strategy, to
authenticate requests.

For example, as route middleware in an [Express](http://expressjs.com/)
application:

    app.post('/auth/nus',
      passport.authenticate('nus', {
        successRedirect: '/',
        failureRedirect: '/auth/login/'
      })
    );

## Credits

  - [Fazli Sapuan](https://github.com/fuzzie360)
  - Based on [passport-ldap](https://github.com/mintbridge/passport-ldap) by [Paul Dixon](https://github.com/mintbridge)

## License

[The MIT License](http://opensource.org/licenses/MIT)

Copyright (c) 2013 Fazli Sapuan <[http://fazli.sapuan.org](http://fazli.sapuan.org)>, passport-ldap Copyright (c) 2011-2013 Paul Dixon <[http://www.mintbridge.co.uk/](http://www.mintbridge.co.uk)>