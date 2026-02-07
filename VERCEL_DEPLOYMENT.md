# Vercel Deployment Guide

## Issue: Blank Page on Vercel

The blank page issue is caused by two things:
1. Missing routing configuration for React Router
2. Missing environment variables

## ✅ Solution

### Step 1: Add vercel.json (Already Done!)
I've created `vercel.json` to handle client-side routing.

### Step 2: Add Environment Variables to Vercel

You need to add your environment variables to Vercel:

1. Go to your Vercel dashboard: https://vercel.com/dashboard
2. Click on your project: `univoice`
3. Go to **Settings** → **Environment Variables**
4. Add these variables:

```
VITE_SUPABASE_URL = https://gwfalqwrkpyclxchqbuz.supabase.co
VITE_SUPABASE_ANON_KEY = sb_publishable_q0Cgw5of-ZJuoNAI0s3Byg_E8yR06Mv
GEMINI_API_KEY = AIzaSyBw3xsCV7moeoA_KOijYQZEUPlQW_X5jcQ
```

**Important:** 
- Make sure to add them for **Production**, **Preview**, and **Development** environments
- The variable names must be EXACTLY as shown (case-sensitive)

### Step 3: Redeploy

After adding the environment variables:
1. Go to **Deployments** tab
2. Click the **three dots** on the latest deployment
3. Click **Redeploy**

OR just push the new `vercel.json` file to GitHub and Vercel will auto-deploy.

## Quick Fix Commands

```bash
# Commit the vercel.json file
git add vercel.json
git commit -m "Add Vercel configuration for routing"
git push

# Vercel will automatically redeploy
```

## Expected Result

After redeployment, your app should:
- ✅ Show the login page at the root URL
- ✅ Handle all routes correctly
- ✅ Connect to Supabase properly

## Troubleshooting

If you still see a blank page:
1. Check browser console (F12) for errors
2. Verify environment variables are set in Vercel
3. Make sure the deployment finished successfully
4. Clear browser cache and hard refresh (Ctrl+Shift+R)
