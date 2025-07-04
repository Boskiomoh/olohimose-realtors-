# EmailJS Setup Instructions for Olohimose Realtors

## Step 1: Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## Step 2: Create Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the setup instructions to connect your email
5. Note down your **Service ID** (e.g., "service_abc123")

## Step 3: Create Email Template
1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template content:

**Subject:** New Contact Form Submission - {{from_name}}

**Content:**
```
Hello,

You have received a new contact form submission from your website.

Submission Details:
- Submission #: {{submission_number}}
- Date: {{submission_date}}

Contact Information:
- Name: {{from_name}}
- Email: {{from_email}}
- Phone: {{phone}}
- Service Interest: {{service}}

Message:
{{message}}

---
This email was sent automatically from your Olohimose Realtors website contact form.
```

4. Note down your **Template ID** (e.g., "template_xyz789")

## Step 4: Get Your Public Key
1. Go to "Account" in your EmailJS dashboard
2. Find your **Public Key** (e.g., "user_abc123xyz")

## Step 5: Update the Contact Form
Replace these placeholders in `src/components/ContactSection.vue`:

```javascript
// Line 126: Replace with your actual public key
emailjs.init("YOUR_PUBLIC_KEY");

// Lines 140-142: Replace with your actual IDs
await emailjs.send(
  'YOUR_SERVICE_ID',    // Replace with your service ID
  'YOUR_TEMPLATE_ID',   // Replace with your template ID
  templateParams
);
```

## Step 6: Test the Form
1. Fill out the contact form on your website
2. Check if the email arrives at info@olohimose.com
3. Verify the submission counter increases

## Email Template Variables Available:
- `{{from_name}}` - Customer's name
- `{{from_email}}` - Customer's email
- `{{phone}}` - Customer's phone (or "Not provided")
- `{{service}}` - Selected service
- `{{message}}` - Customer's message
- `{{to_email}}` - Your email (info@olohimose.com)
- `{{submission_date}}` - Date and time of submission
- `{{submission_number}}` - Sequential submission number

## Features Included:
✅ Email notifications for each form submission
✅ Professional email templates
✅ Form validation
✅ Success/error messages
✅ Loading states
✅ Submission counter (tracks total inquiries)
✅ Mobile responsive design
✅ Required field validation

## Free Tier Limits:
- 200 emails per month
- Perfect for small to medium businesses
- No credit card required

## Troubleshooting:
- Make sure all IDs are correctly replaced
- Check your email service connection in EmailJS dashboard
- Verify your email template is active
- Check browser console for any error messages

Your contact form will now send professional emails directly to info@olohimose.com with all the customer details!