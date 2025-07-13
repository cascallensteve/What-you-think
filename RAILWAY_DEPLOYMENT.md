# Railway Deployment Guide

## Prerequisites
- GitHub repository with your Django code
- Railway account (sign up at railway.com)
- Supabase database (already configured)

## Deployment Steps

### 1. Deploy to Railway
1. Go to **https://railway.com**
2. Sign up/login with GitHub
3. Click **New Project**
4. Select **Deploy from GitHub repo**
5. Choose **What-you-think** repository
6. Click **Deploy Now**

### 2. Configure Environment Variables
In Railway dashboard, click your app → **Variables** tab:

```
DB_NAME=postgres
DB_USER=postgres.rpptvbcjrytijmfqvndj
DB_PASSWORD=Stevoh@Stevoh2020.
DB_HOST=aws-0-eu-north-1.pooler.supabase.com
DB_PORT=6543
SECRET_KEY=your-django-secret-key
DEBUG=False
TOGETHER_API_KEY=your-together-api-key
```

### 3. Generate Domain
1. Go to **Settings** → **Networking**
2. Click **Generate Domain**
3. Your app will be live at the generated URL

## Files for Railway
- `Procfile` - Startup command
- `nixpacks.toml` - Build configuration
- `requirements.txt` - Dependencies including gunicorn
- `whisperlink_backend/settings.py` - Railway-compatible settings

## Notes
- Uses existing Supabase database (no Railway PostgreSQL needed)
- Automatic static file collection and migrations
- HTTPS enabled by default
- Custom domain support available
