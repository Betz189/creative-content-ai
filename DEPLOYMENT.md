# Deployment Guide

## Prerequisites
1. Supabase account and project
2. OpenAI API key
3. Vercel/Netlify account (for hosting)

## Setup Steps

### 1. Supabase Setup
1. Create a new Supabase project
2. Run the SQL queries from the database setup
3. Deploy the edge functions:
   ```bash
   supabase functions deploy generate-content
   supabase functions deploy manage-subscription
   ```
4. Set environment variables in Supabase dashboard:
   - `OPENAI_API_KEY`: Your OpenAI API key

### 2. Environment Variables
Create `.env` file with:
```
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

### 3. Deploy to Vercel
1. Connect your GitHub repo to Vercel
2. Add environment variables in Vercel dashboard
3. Deploy automatically

### 4. Deploy to Netlify
1. Connect your GitHub repo to Netlify
2. Build command: `npm run build`
3. Publish directory: `dist`
4. Add environment variables in Netlify dashboard

## Build Commands
- Development: `npm run dev`
- Production build: `npm run build`
- Preview: `npm run preview`