# Google Form Setup Instructions

## Step 1: Create Google Form

1. Go to https://forms.google.com
2. Login with: **dnssijuaalumni@gmail.com** / **Rkc2300436@**
3. Create a new form titled "DNS Alumni Registration"
4. Add the following fields (matching your PDF form):

### Required Fields:
- **Full Name of Alumnus** (Short answer - Required)
- **Designation / Current Profession** (Short answer - Required)
- **Mobile Number** (Short answer - Required)
- **Email Address** (Short answer - Optional)
- **Year of Passing** (Short answer - Required)
- **UPI Transaction ID** (Short answer - Required)
- **Permanent Address** (Paragraph - Optional)

## Step 2: Get Form POST URL

1. In your Google Form, click the **three dots (⋮)** in the top right
2. Click **"Get pre-filled link"** (this helps you see the form structure)
3. Open the form in a new tab
4. Right-click on the form and select **"Inspect"** or press **F12**
5. Go to the **Network** tab
6. Fill out the form and click **Submit**
7. Look for a request to `formResponse` - this will show you the POST URL
8. The URL will look like: `https://docs.google.com/forms/d/e/FORM_ID/formResponse`

**OR use this method:**
1. Open your Google Form
2. Click **Send** button (top right)
3. Click the **</>** (HTML embed) icon
4. Copy the form ID from the embed code
5. The POST URL format is: `https://docs.google.com/forms/d/e/FORM_ID/formResponse`

## Step 3: Get Field Entry IDs

1. Open your Google Form
2. Right-click on the form page and select **"View Page Source"** or press **Ctrl+U**
3. Press **Ctrl+F** and search for `"entry.`
4. You'll see entries like:
   - `entry.123456789` for Full Name
   - `entry.987654321` for Mobile Number
   - etc.
5. Note down each field's entry ID

**OR use this method:**
1. Fill out your form once and submit it
2. Go to the Google Sheet linked to the form
3. The column headers will show the field names
4. Use browser inspector to find the entry IDs (see method above)

## Step 4: Update HTML Form

Once you have:
- Form POST URL
- Entry IDs for each field

Update the `index.html` file:
1. Replace `PASTE_GOOGLE_FORM_POST_URL_HERE` with your actual POST URL
2. Replace all `entry.1111111111`, `entry.2222222222`, etc. with your actual entry IDs

## Current Form Fields in HTML:

```html
- Full Name: entry.1111111111 → Replace with actual entry ID
- Designation: entry.7777777777 → Replace with actual entry ID  
- Mobile: entry.2222222222 → Replace with actual entry ID
- Email: entry.3333333333 → Replace with actual entry ID
- Year of Passing: entry.4444444444 → Replace with actual entry ID
- UPI Transaction ID: entry.5555555555 → Replace with actual entry ID
- Address: entry.6666666666 → Replace with actual entry ID
```

## Quick Method Using Browser Extension:

1. Install "FormRanger" or similar Chrome extension
2. Or use this JavaScript in browser console on your Google Form page:
```javascript
// Run this in browser console on your Google Form page
document.querySelectorAll('input, textarea, select').forEach((el, i) => {
  if(el.name && el.name.startsWith('entry.')) {
    console.log(`Field ${i+1}: ${el.name} - Label: ${el.closest('.freebirdFormviewerViewItemsItemItem')?.querySelector('label')?.textContent || 'N/A'}`);
  }
});
```

## Important Notes:

- Make sure your Google Form accepts responses
- The form should be set to collect email addresses (optional)
- Test the form submission after updating the HTML
- The form will open in a new tab (`target="_blank"`) after submission
