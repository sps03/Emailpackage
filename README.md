# Emailpackage
// Example of how to call the functions <br />
const { sendFavMail } = require('mg-newsletter'); <br />

const emailTemplate = {<br />
  subject: 'Test Subject',<br />
  body: 'Hello {{Username}}, Your email is {{email}}'<br />
};<br />

const smtpConfig = {<br />
  host: 'smtp.gmail.com',<br />
  port: 587,<br />
  secure: false,<br />
  user: process.env.YOUR_EMAIL_ID,//replace with your ID in env file <br />
  pass: process.env.EMAILKEY // replace with your EmailKEY in env file <br />

 //How to get EMAILKEY <br />
 1.Go to email settings <br />
 2.Complete 2step verification <br />
 3.Then get your App Key <br />

};<br />



Example usage: <br />
const { sendEmail } = require('mg_newsletter');<br />
const dotenv = require('dotenv');<br />
dotenv.config();<br />
const userData = {<br />
  email: 'user@example.com',<br />
  avatar: 'avatar-url',<br />
  firstName: 'John',<br />
  lastName: 'Doe',<br />
  useFor: 'favCompanyJobSubmission',<br />
  companyName: 'OLA',<br />
  jobTitle: 'Software Engineer Intern',<br />
  jobDescription: 'Proficiency in C++, DSA and OOPS'<br />
};


// Call sendEmail function based on the user's requirement<br />
// For signup:<br />
sendEmail('signup', userData)<br />
  .then(() => console.log('Signup email sent'))<br />
  .catch(error => console.error('Error sending signup email:', error));<br />

// For login:<br />
sendEmail('login', userData)<br />
  .then(() => console.log('Login email sent'))<br />
  .catch(error => console.error('Error sending login email:', error));<br />

// // For payment successful:<br />
sendEmail('paymentSuccessful', userData)<br />
  .then(() => console.log('Payment successful email sent'))<br />
  .catch(error => console.error('Error sending payment successful email:', error));<br />
