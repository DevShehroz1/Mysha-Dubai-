# Contact Form Email Setup Instructions

## Current Implementation

I've set up your contact form to send emails to **info@myshaproperties.co** using a mailto: link. When users fill out the form and click submit, it will:
1. Collect all form data (Name, Email, Phone, Message)
2. Open their default email client with a pre-filled email to info@myshaproperties.co
3. Show a success message

## Limitations of Current Solution

The mailto: approach has some limitations:
- Requires users to have an email client configured
- May not work on all mobile devices
- Users need to manually send the email after it opens
- No automatic email delivery guarantee

## Better Alternatives (Recommended)

### Option 1: Formspree (Easiest - Free Tier Available)

**Steps:**
1. Go to https://formspree.io and create a free account
2. Create a new form
3. Set the recipient email to: **info@myshaproperties.co**
4. Copy your Formspree form ID (looks like: `xvgkqxyz`)
5. In the HTML file, find the form and replace the action URL:
   - Current: `action="mailto:info@myshaproperties.co"`
   - Replace with: `action="https://formspree.io/f/YOUR_FORM_ID"`
6. Remove or comment out the `onsubmit="return handleFormSubmit(event)"` attribute
7. The form will automatically send emails to your address

**Free tier includes:** 50 submissions/month

### Option 2: EmailJS (Free Tier - 200 emails/month)

**Steps:**
1. Sign up at https://www.emailjs.com (free account)
2. Create an email service (Gmail, Outlook, etc.)
3. Create an email template
4. Get your Service ID, Template ID, and Public Key
5. Add EmailJS script to your HTML:
   ```html
   <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
   ```
6. Replace the handleFormSubmit function with EmailJS code (see example in HTML comments)

### Option 3: Backend API (Most Professional)

If you have a backend server (Node.js, PHP, Python, etc.), you can:
1. Create an API endpoint that receives form data
2. Use a service like SendGrid, Mailgun, or AWS SES to send emails
3. Update the form to POST to your API endpoint

### Option 4: Google Apps Script (Free)

1. Create a Google Apps Script
2. Deploy it as a web app
3. Use it as your form endpoint
4. Configure it to send emails to info@myshaproperties.co

## Quick Fix: Update Current Implementation

If you want to keep the current mailto: solution but improve it, the code is already in place. The form will work as-is.

## Testing

To test the current implementation:
1. Fill out the form with test data
2. Click Submit
3. Your email client should open with a pre-filled email
4. Check that all form data is included in the email body

## Need Help?

If you need help setting up any of these alternatives, let me know which option you prefer and I can help you implement it!
