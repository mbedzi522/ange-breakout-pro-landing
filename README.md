Range Breakout Pro EA Landing Page - Vercel Deployment Guide

Overview

This guide will walk you through deploying your Range Breakout Pro EA landing page to Vercel. Vercel is the perfect platform for Next.js applications and provides seamless deployment with automatic builds and environment variable management.

Prerequisites

•
A GitHub account (free)

•
A Vercel account (free) - sign up at https://vercel.com

•
The project files (range-breakout-landing.zip)

Step 1: Prepare Your Project

1.1 Extract Project Files

1.
Extract the range-breakout-landing.zip file to your computer

2.
Open the extracted folder

1.2 Create GitHub Repository

1.
Go to https://github.com and sign in

2.
Click "New repository" (green button)

3.
Name it: range-breakout-pro-landing

4.
Make it Public (required for free Vercel deployment)

5.
Click "Create repository"

1.3 Upload Project to GitHub

Option A: Using GitHub Web Interface (Easier)

1.
In your new repository, click "uploading an existing file"

2.
Drag and drop ALL files from the extracted project folder

3.
Write commit message: "Initial landing page setup"

4.
Click "Commit changes"

Option B: Using Git Commands (if you have Git installed)

Bash


cd path/to/range-breakout-landing
git init
git add .
git commit -m "Initial landing page setup"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/range-breakout-pro-landing.git
git push -u origin main


Step 2: Deploy to Vercel

2.1 Connect Vercel to GitHub

1.
Go to https://vercel.com and sign in

2.
Click "New Project"

3.
Click "Continue with GitHub"

4.
Authorize Vercel to access your GitHub account

2.2 Import Your Repository

1.
Find your range-breakout-pro-landing repository

2.
Click "Import"

3.
Vercel will automatically detect it's a Next.js project

2.3 Configure Project Settings

1.
Project Name: range-breakout-pro-landing (or your preferred name)

2.
Framework Preset: Next.js (should be auto-detected)

3.
Root Directory: ./ (leave as default)

4.
Build Command: npm run build (should be auto-filled)

5.
Output Directory: .next (should be auto-filled)

6.
Install Command: npm install (should be auto-filled)

2.4 Add Environment Variables

Click "Environment Variables" and add these (you can use placeholder values for now):

Plain Text


NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_placeholder_key_for_demo
CLERK_SECRET_KEY=sk_test_placeholder_key_for_demo
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_placeholder_key_for_demo
STRIPE_SECRET_KEY=sk_test_placeholder_key_for_demo
STRIPE_WEBHOOK_SECRET=whsec_placeholder_secret_for_demo
RESEND_API_KEY=re_placeholder_key_for_demo
NEXT_PUBLIC_APP_URL=https://your-project-name.vercel.app
PRESALE_LIMIT=500
PRESALE_PRICE=19700
REGULAR_PRICE=49700


Important: Replace your-project-name with your actual Vercel project name.

2.5 Deploy

1.
Click "Deploy"

2.
Wait for the build to complete (usually 2-3 minutes)

3.
You'll get a live URL like: https://your-project-name.vercel.app

Step 3: Verify Deployment

3.1 Test Your Site

1.
Click on the provided URL

2.
Verify the landing page loads correctly

3.
Test the demo checkout buttons

4.
Check mobile responsiveness

5.
Verify the countdown timer works

6.
Check the progress bar (347/500 sales)

3.2 Update App URL

1.
Go back to Vercel dashboard

2.
Click on your project

3.
Go to "Settings" → "Environment Variables"

4.
Update NEXT_PUBLIC_APP_URL with your actual Vercel URL

5.
Click "Save"

6.
Go to "Deployments" and click "Redeploy" on the latest deployment

Step 4: Configure Production APIs (When Ready)

When you're ready to go live with real payments and authentication:

4.1 Clerk Authentication

1.
Sign up at https://clerk.com

2.
Create a new application

3.
Get your production API keys

4.
Update environment variables in Vercel:

•
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY

•
CLERK_SECRET_KEY



4.2 Stripe Payments

1.
Sign up at https://stripe.com

2.
Complete business verification

3.
Get your live API keys

4.
Update environment variables in Vercel:

•
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY

•
STRIPE_SECRET_KEY

•
STRIPE_WEBHOOK_SECRET



4.3 Resend Email

1.
Sign up at https://resend.com

2.
Verify your domain

3.
Get your API key

4.
Update environment variable in Vercel:

•
RESEND_API_KEY



4.4 Database (Optional)

For production with real user data:

1.
Set up a PostgreSQL database (Supabase recommended)

2.
Update DATABASE_URL environment variable

Step 5: Custom Domain (Optional)

5.1 Add Custom Domain

1.
In Vercel dashboard, go to your project

2.
Click "Settings" → "Domains"

3.
Add your custom domain (e.g., rangebreakoutpro.com)

4.
Follow Vercel's DNS configuration instructions

5.2 Update Environment Variables

1.
Update NEXT_PUBLIC_APP_URL to your custom domain

2.
Update API webhook URLs in Stripe/Clerk to use your custom domain

Step 6: Ongoing Management

6.1 Making Updates

1.
Make changes to your local project files

2.
Commit and push to GitHub

3.
Vercel automatically rebuilds and deploys

6.2 Monitoring

•
Check Vercel dashboard for deployment status

•
Monitor analytics in Vercel dashboard

•
Set up error tracking if needed

6.3 Environment Variables Management

•
Update API keys through Vercel dashboard

•
Never commit sensitive keys to GitHub

•
Use different keys for development and production

Troubleshooting

Common Issues

Build Fails

•
Check the build logs in Vercel dashboard

•
Ensure all dependencies are in package.json

•
Verify environment variables are set correctly

Site Loads but Features Don't Work

•
Check environment variables are set

•
Verify API keys are valid

•
Check browser console for errors

Styling Issues

•
Clear browser cache

•
Check if CSS files are loading correctly

•
Verify Tailwind CSS is building properly

API Routes Not Working

•
Ensure API routes are in the correct folder structure

•
Check Vercel function logs

•
Verify environment variables for API routes

Getting Help

•
Vercel Documentation: https://vercel.com/docs

•
Vercel Community: https://github.com/vercel/vercel/discussions

•
Next.js Documentation: https://nextjs.org/docs

Security Best Practices

1.
Environment Variables: Never commit API keys to GitHub

2.
HTTPS: Vercel provides HTTPS by default

3.
API Keys: Rotate keys regularly

4.
Webhooks: Verify webhook signatures

5.
CORS: Configure CORS for API routes if needed

Performance Optimization

1.
Images: Use Next.js Image component (already implemented)

2.
Caching: Vercel handles caching automatically

3.
CDN: Vercel provides global CDN

4.
Analytics: Enable Vercel Analytics for performance monitoring

Your Range Breakout Pro EA landing page is now live and ready to start collecting presales! 🚀

Quick Checklist




Project uploaded to GitHub




Deployed to Vercel




Environment variables configured




Site loads correctly




Demo functionality works




Mobile responsive




SEO meta tags working




Ready for production API keys

Your live site URL: https://your-project-name.vercel.app

Remember to replace the placeholder API keys with real ones when you're ready to go live!

