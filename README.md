# Emailpackage

This package allows you to easily send emails using various templates for different purposes.

## Installation

You can install this package via npm: 

```bash
npm install mg-email-package
```

## Usage
First, require the necessary function(s) from the package:
```bash
const { sendFavMail } = require('mg-email-package');


Next, configure the SMTP settings:
const smtpConfig = {
  host: 'smtp.gmail.com',
  port: 587,
  secure: false,
  user: process.env.YOUR_EMAIL_ID, // replace with your email ID from env file
  pass: process.env.EMAILKEY // replace with your email key from env file
};

```

## To obtain the EMAILKEY, follow these steps:
```bash
1. Go to your email settings.
2. Complete 2-step verification.
3. Obtain your App Key.
```

## Make sure to add these values to your ENV file:
```bash
EMAILKEY
YOUR_EMAIL_ID
RECIPIENT
```


### Example usage:
```bash
const { sendEmail } = require('mg_newsletter');
const dotenv = require('dotenv');
dotenv.config();

const userData = {
  email: 'user@example.com',
  avatar: 'avatar-url',
  firstName: 'John',
  lastName: 'Doe',
  useFor: 'favCompanyJobSubmission',
  companyName: 'OLA',
  jobTitle: 'Software Engineer Intern',
  jobDescription: 'Proficiency in C++, DSA and OOPS'
};

// Call sendEmail function based on the user's requirement
// For signup:
sendEmail('signup', userData)
  .then(() => console.log('Signup email sent'))
  .catch(error => console.error('Error sending signup email:', error));

// For login:
sendEmail('login', userData)
  .then(() => console.log('Login email sent'))
  .catch(error => console.error('Error sending login email:', error));

// For payment successful:
sendEmail('paymentSuccessful', userData)
  .then(() => console.log('Payment successful email sent'))
  .catch(error => console.error('Error sending payment successful email:', error));
```

Replace placeholders like YOUR_EMAIL_ID, EMAILKEY, and RECIPIENT with the actual values. Make sure your package's functions (sendFavMail, sendEmail) are correctly documented, and their usage is explained in the README.md file.