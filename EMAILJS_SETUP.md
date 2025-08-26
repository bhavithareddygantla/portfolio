# EmailJS Setup Guide

This guide will help you set up EmailJS to make the contact form actually send emails.

## 🚀 Step-by-Step Setup

### 1. Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

### 2. Add Email Service
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" (or your preferred email provider)
4. Connect your email account (bhavithareddygantla124@gmail.com)
5. Note down the **Service ID** (e.g., `service_abc123`)

### 3. Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Configure the template:

**Template Settings:**
- **Template Name**: Portfolio Contact Form
- **To Email**: `bhavithareddygantla124@gmail.com` (set this directly in the template)
- **From Email**: Your Gmail address (the one connected to EmailJS)
- **Subject**: `New message from {{from_name}} - {{subject}}`

**Email Body:**
```
Hello {{to_name}},

You have received a new message from your portfolio website:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio contact form.
Reply to: {{reply_to}}
```

**Important:** Make sure to set the "To Email" field directly in the template to `bhavithareddygantla124@gmail.com`

4. Save the template and note down the **Template ID** (e.g., `template_xyz789`)

### 4. Get Public Key
1. Go to "Account" → "API Keys"
2. Copy your **Public Key**

### 5. Update the Code
Replace the placeholders in `script.js`:

```javascript
// Line 3: Replace YOUR_PUBLIC_KEY
emailjs.init("your_actual_public_key_here");

// Line 67: Replace YOUR_SERVICE_ID and YOUR_TEMPLATE_ID
emailjs.send('your_service_id_here', 'your_template_id_here', templateParams)
```

### Example:
```javascript
emailjs.init("user_abc123def456ghi789");
emailjs.send('service_xyz789', 'template_abc123', templateParams)
```

## 📧 How It Works

1. **User fills form** → Form data is collected
2. **Validation** → Checks all fields and email format
3. **EmailJS sends email** → Uses your Gmail account
4. **Success/Error notification** → Shows user feedback
5. **Form resets** → Ready for next message

## 🔧 Features

- ✅ **Real email delivery** to your inbox
- ✅ **Professional notifications** (no alerts)
- ✅ **Form validation** with error messages
- ✅ **Loading states** during sending
- ✅ **Auto-reset** after successful submission
- ✅ **Error handling** with user feedback

## 🎯 Benefits

- **No backend required** - Works with static hosting
- **Free tier available** - 200 emails/month free
- **Professional appearance** - Beautiful notifications
- **Reliable delivery** - Uses your existing email
- **Easy setup** - Just replace 3 values

## 🚨 Important Notes

1. **Keep your keys secure** - Don't share them publicly
2. **Test thoroughly** - Send test emails to yourself
3. **Monitor usage** - Check EmailJS dashboard for limits
4. **Backup emails** - Consider multiple email services

## 🆘 Troubleshooting

**Form not sending:**
- Check browser console for errors
- Verify all IDs are correct
- Ensure EmailJS is loaded

**Emails not received:**
- Check spam folder
- Verify email service connection
- Test with different email

**Recipient address is empty:**
- In EmailJS dashboard, go to "Email Templates"
- Edit your template (`template_zpq6jow`)
- In the template settings, set "To Email" field to: `bhavithareddygantla124@gmail.com`
- **Do NOT use** `{{to_email}}` in the To Email field
- Save the template and test again

**Validation errors:**
- Check form field IDs
- Ensure all required fields are filled
- Verify email format

## 📞 Support

If you need help:
1. Check EmailJS documentation
2. Review browser console errors
3. Test with EmailJS examples
4. Contact EmailJS support

---

**Your contact form will now send real emails to bhavithareddygantla124@gmail.com!** 🎉
