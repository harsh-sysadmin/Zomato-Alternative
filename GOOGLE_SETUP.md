# Real Google OAuth Setup Instructions

## Step 1: Create Google Cloud Project
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Name it "Zomato Clone" or similar

## Step 2: Configure OAuth Consent Screen (Required First)
1. Go to "APIs & Services" > "OAuth consent screen"
2. Choose "External" user type
3. Fill required fields:
   - App name: "Zomato Clone"
   - User support email: your email
   - Developer contact: your email
4. Click "Save and Continue" through all steps

## Step 3: Create OAuth 2.0 Client ID
1. Go to "APIs & Services" > "Credentials"
2. Click "+ CREATE CREDENTIALS"
3. Select "OAuth client ID"
4. If prompted, configure consent screen first (see Step 2)
5. Choose "Web application" as application type
6. **Name:** "Zomato Clone Web Client"
7. **Authorized JavaScript origins:**
   - `http://localhost:3000`
   - `https://localhost:3000` (if using HTTPS)
8. **Authorized redirect URIs:** (Leave empty for Google Identity Services)
9. Click "Create"
10. Copy the Client ID from the popup

## Step 3.1: Additional Configuration
1. Go back to "OAuth consent screen"
2. Add test users (your Gmail address) in "Test users" section
3. Save changes

## Step 4: Update Environment Variables
1. Open `.env` file in project root (d:\zomato-clone\.env)
2. Find line: `REACT_APP_GOOGLE_CLIENT_ID=YOUR_REAL_GOOGLE_CLIENT_ID_HERE`
3. Replace `YOUR_REAL_GOOGLE_CLIENT_ID_HERE` with your real Client ID
4. Save the file
5. Restart your React app (`npm start`)

**Example:**
```
REACT_APP_GOOGLE_CLIENT_ID=123456789-abc123def456.apps.googleusercontent.com
```

## Step 5: Test Real Authentication
- Click "Continue with Google" 
- Real Google popup will appear
- Select your Google account
- Grant permissions
- You'll be logged in with real Google data

## Troubleshooting "Can't continue with google.com" Error:
1. **Check Client ID:** Ensure it's correctly copied in .env file
2. **Authorized Origins:** Must include `http://localhost:3000`
3. **Test Users:** Add your Gmail to test users in OAuth consent screen
4. **App Status:** Set OAuth app to "Testing" mode initially
5. **Clear Browser Cache:** Clear cookies and try again
6. **Restart App:** After changing .env, restart with `npm start`

## Current Status
✅ Google Identity Services library loaded
✅ Real OAuth flow implemented  
✅ JWT token decoding
✅ User data extraction (name, email, photo)
⚠️  Need real Client ID for production use

## Security Notes
- Never commit real Client IDs to public repos
- Use environment variables for sensitive data
- Validate tokens on backend for production apps