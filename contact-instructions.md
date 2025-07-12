# Contact Form Setup Instructions

## Option 1: EmailJS (Current Setup)

1. **Create EmailJS Account:**
   - Go to https://www.emailjs.com/
   - Sign up for a free account
   - Create a new email service (Gmail recommended)

2. **Get Your Credentials:**
   - Public Key: Found in your EmailJS dashboard
   - Service ID: Created when you add an email service
   - Template ID: Created when you make a template

3. **Create Email Template:**
   Use these variables in your template:
   - `{{name}}` - Sender's name
   - `{{email}}` - Sender's email  
   - `{{message}}` - Message content

4. **Update Your Code:**
   Replace in `index.html`:
   ```javascript
   emailjs.init("9lVyryK1S8P-PT3Pa"); // Replace with actual public key
   emailjs.send('service_24jnbfb', 'template_0iejcln', templateParams)
   ```

   Replace in `SRC/script/script.js`:
   ```javascript
   const serviceID = "service_24jnbfb";
   const templateID = "template_0iejcln";
   ```

## Option 2: Web3Forms (Simpler Alternative)

If you want an easier setup without API keys:

1. Go to https://web3forms.com/
2. Enter your email to get an access key
3. Replace the form action in your HTML:
   ```html
   <form action="https://api.web3forms.com/submit" method="POST">
   <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY">
   <!-- your form fields -->
   </form>
   ```

## Testing Your Form

1. Fill out the form with test data
2. Check your email inbox for messages
3. Check browser console for any errors
4. Verify the success message appears

## Common Issues

- **CORS Errors**: Make sure your domain is added to EmailJS settings
- **Template Variables**: Ensure template variables match your JavaScript
- **Public Key**: Make sure you're using the public key, not private key
- **Service Status**: Check if your EmailJS service is active

## Support

If you need help with setup, I can assist you with either option!
