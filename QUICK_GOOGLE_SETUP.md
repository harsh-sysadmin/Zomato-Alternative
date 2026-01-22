# Quick Google OAuth Setup (Working Solution)

## 1. Get Google Client ID (5 minutes)
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create new project: "Zomato Clone"
3. Go to "APIs & Services" > "OAuth consent screen"
   - Choose "External"
   - App name: "Zomato Clone"
   - Your email for support and developer contact
   - Save and continue through all steps
4. Go to "APIs & Services" > "Credentials"
   - Click "CREATE CREDENTIALS" > "OAuth client ID"
   - Choose "Web application"
   - Authorized JavaScript origins: `http://localhost:3000`
   - Click "Create"
   - Copy the Client ID

## 2. Update .env File
Open `d:\zomato-clone\.env` and replace:
```
REACT_APP_GOOGLE_CLIENT_ID=YOUR_ACTUAL_CLIENT_ID_HERE
```

## 3. Restart App
```bash
npm start
```

## 4. Test
- Click "Continue with Google"
- Official Google sign-in button appears
- Select your Google account
- Done!

## What Changed
✅ Uses official Google Sign-In button (more reliable)
✅ Simplified implementation
✅ Better error handling
✅ Works with any valid Google Client ID

The new implementation uses Google's official sign-in button which is more stable and handles all the OAuth complexity automatically.