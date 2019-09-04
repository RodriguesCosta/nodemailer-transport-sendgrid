# nodemailer-transport-sendgrid

This module is a transport plugin for Nodemailer that makes it possible to send through SendGrid's Web API!

# Usage

### Install unsing npm
```
npm install nodemailer-transport-sendgrid --save
```
or using yarn
```
yarn add nodemailer-transport-sendgrid
```

### Require the module and initialize it with your SendGrid apiKey.

```JS
const nodemailer = require('nodemailer');
const nmTransportSg = require('nodemailer-transport-sendgrid');

const mailer = nodemailer.createTransport(nmTransportSg('SENDGRID_API_KEY'));
```
Note: We suggest storing your SendGrid apiKey as enviroment variables.

### Create an email and send it off!

```JS
const email = {
  to: 'email@recipient.com',
  from: 'email@sender.com',
  subject: 'Email confirmation',
  text: 'Visit the link to confirm your email...',
  html: '<b>Visit the link to confirm your email...</b>',
  category: 'EMAIL_CONFIRMATION', // This parameter is optional, it will make your email into a sendgrid category.
};
 
mailer.sendMail(email)
  .then(console.log)
  .catch(console.error);
```
