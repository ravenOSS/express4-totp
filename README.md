# express4-totp
This is an update to the example from jaredhanson's passport-totp.
Provide code boilerplate
Express migrated from 3.x to 4.x
Dependencies modified
Routes broken out to new folder/file

TODO
Move routes to file
Review packages
- thirty-two
- connect-ensure-login // remembers requested route to return to after login

app.get('/login', function(req, res) {
  res.render('login');
});

app.post('/login', passport.authenticate('local', { successReturnToOrRedirect: '/', failureRedirect: '/login' }));

- express-flash // replace with connect-flash. EF just a wrapper
- express-session = needs session store instead of dev memory store for production. Use connect-mongodb-session (karpov). Not the recommended package that seems to have a maintenance issue. Express-session no longer requires cookie-parser and may cause problems if the secret is not the same.