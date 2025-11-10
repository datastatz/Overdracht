# AI Scanity - Quality Control API

> **API for quality control of installation photos for technicians**

This system allows technicians to submit photos of appliance installations (washing machines, dryers, etc.) and receive automated quality control feedback using AI.

---



## 🚀 Quick Start - Production Deployment (10 minutes)

**This guide will get your API live in production in just 10 minutes!**

### Prerequisites Checklist

- [ ] OpenAI API Key ([Get it here](https://platform.openai.com/api-keys))
- [ ] Supabase Account ([Sign up](https://supabase.com/))
- [ ] Railway Account ([Sign up](https://railway.app/))
- [ ] Vercel Account ([Sign up](https://vercel.com/))
- [ ] GitHub Account ([Sign up](https://github.com/))

### Deployment Steps

1. **GitHub** (2 min): Upload code to GitHub repository
2. **Supabase** (1 min): Accept database transfer - **No SQL setup needed!**
3. **Railway** (3 min): Deploy Go API from GitHub
4. **Vercel** (3 min): Deploy dashboard from GitHub
5. **Test** (1 min): Submit test photo and verify response
x
✅ **Database is pre-configured!** You'll receive a Supabase project transfer with all tables, users, and API keys already set up.

Let's get started! 👇

## 📦 Prerequisites

Before deploying to production, you need:

### Accounts Required 
- **OpenAI API Key** - For AI image analysis ([Get one here](https://platform.openai.com/api-keys))
- **Supabase Account** - Database hosting ([Sign up](https://supabase.com/))
- **Railway Account** - Go API hosting ([Sign up](https://railway.app/))
- **Vercel Account** - Dashboard hosting ([Sign up](https://vercel.com/))
- **GitHub Account** - Code repository ([Sign up](https://github.com/))

---

## Step 1: GitHub Setup

**Time: 2 minutes**

You will receive a ZIP file with the complete codebase. Let's get it on GitHub:

### 1.1 Extract and Navigate

1. **Extract the ZIP file** to your desired location
2. **Open Terminal** (Mac/Linux) or **Command Prompt** (Windows)
3. Navigate to the project folder:

```bash
cd /path/to/api-Q
```

### 1.2 Create GitHub Repository

1. Go to [https://github.com/new](https://github.com/new)
2. Fill in:
   - **Repository name**: `ai-scanity-api` (or your preferred name)
   - **Visibility**: Choose **Private** (recommended for production)
   - **DO NOT** check "Initialize with README, .gitignore, or license"
3. Click **"Create repository"**

### 1.3 Push Code to GitHub

Copy and paste these commands in your terminal:

```bash
# Initialize git (if not already initialized)
git init

# Add all files
git add .

# Make first commit
git commit -m "Initial commit - AI Scanity Quality Control API"

# Add your GitHub repository as remote (replace with YOUR repository URL)
git remote add origin https://github.com/your-username/ai-scanity-api.git

# Push to GitHub
git branch -M main
git push -u origin main
```

✅ **Done!** Your code is now on GitHub and ready for deployment

---

## Step 2: Accept Supabase Transfer

**Time: 1 minute**

🎉 **Good news!** The database is already fully configured. You just need to accept the transfer.

### 2.1 Create Supabase Organization

1. Go to [https://supabase.com/dashboard](https://supabase.com/dashboard)
2. Sign up or log in to your Supabase account
3. Click your profile (top right) → **"New Organization"**
4. Fill in:
   - **Organization name**: Your company name (e.g., "My Company")
   - **Plan**: Choose **"Free"** ✅
5. Click **"Create Organization"**

### 2.2 Invite Developer for Transfer

1. In your new organization, go to **Settings** → **Team**
2. Click **"Invite"**
3. Enter the developer's email: **amellouk1000@gmail.com**
4. Choose role: **"Owner"**
5. Click **"Send Invitation"**

### 2.3 Accept Project Transfer

Once the developer accepts your invitation, they will transfer the **API-Q** project to your organization.

You'll receive an email notification when the transfer is complete.

### 2.4 Get Your API Keys

After the transfer is complete:

1. Go to your Supabase project: **API-Q**
2. Click **Settings** → **API**
3. Copy these values (you'll need them for Railway and Vercel):
   - **Project URL** (e.g., `https://vxacbnrxpnzulhgnknjp.supabase.co`)
   - **anon public** key (starts with `eyJ...`)
   - **service_role** key (starts with `eyJ...`) ⚠️ Keep this secret!


✅ **Done!** Your database is ready with:
- ✅ All tables created (user_profiles, api_keys, requests)
- ✅ Admin account configured
- ✅ Test API keys generated
- ✅ Security policies enabled

---

## Step 3: Deploy Go API (Railway)

**Time: 3 minutes**

### 3.1 Create Railway Project

1. Go to [https://railway.app/](https://railway.app/)
2. Click **"Start a New Project"**
3. Choose **"Deploy from GitHub repo"**
4. Select your repository
5. Railway will auto-detect it's a Go project

### 3.2 Configure Environment Variables

1. In your Railway project, click on the service
2. Go to **"Variables"** tab
3. Add these environment variables (use the values from Supabase Step 2.4):

| Variable Name | Value | Where to get it |
|--------------|-------|-----------------|
| `OPENAI_API_KEY` | `sk-proj-...` | [OpenAI Platform](https://platform.openai.com/api-keys) |
| `SUPABASE_URL` | `https://xxx.supabase.co` | Supabase → Settings → API → Project URL |
| `SUPABASE_SERVICE_ROLE_KEY` | `eyJ...` | Supabase → Settings → API → service_role key |

4. Click **"Add"** for each variable

### 3.3 Configure Domain

1. Go to **"Settings"** tab
2. Scroll to **"Networking"**
3. Click **"Generate Domain"**
4. Your API will be available at: `https://your-project.up.railway.app`
5. Copy this URL - you'll need it for the dashboard!

### 3.4 Deploy

1. Railway will automatically deploy your API
2. Check the **"Deployments"** tab to see progress
3. Once it shows "Success", your API is live! 🎉

⚠️ **Important**: Copy your Railway URL (e.g., `https://ai-scanity-production.up.railway.app`) - you'll need it for Vercel!

---

## Step 4: Deploy Dashboard (Vercel)

**Time: 3 minutes**

### 4.1 Import Project to Vercel

1. Go to [https://vercel.com/](https://vercel.com/)
2. Click **"Add New..."** → **"Project"**
3. Click **"Import"** next to your GitHub repository
4. **Important**: Set **"Root Directory"** to `dashboard`
5. Click **"Continue"**

### 4.2 Configure Environment Variables

In the "Configure Project" screen, add these environment variables:

| Variable Name | Value | Where to get it |
|--------------|-------|-----------------|
| `NEXT_PUBLIC_SUPABASE_URL` | `https://xxx.supabase.co` | Supabase → Settings → API → Project URL |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | `eyJ...` | Supabase → Settings → API → anon public key |
| `NEXT_PUBLIC_API_URL` | `https://xxx.up.railway.app` | Your Railway URL from Step 3 |

⚠️ **Important**: Use the Railway URL you got in Step 3!

### 4.3 Deploy

1. Click **"Deploy"**
2. Wait 2-3 minutes for the build to complete
3. Once done, click **"Visit"** to see your dashboard
4. Your dashboard will be at: `https://your-project.vercel.app`

### 4.4 Login to Dashboard

1. Go to your Vercel URL
2. Login with the **admin email and password** provided by the developer
3. You should see the admin dashboard! 🎉

---

## Step 5: Test Your Deployment

**Time: 1 minute**

Let's verify everything is working!

### 5.1 Test the API

Use the test API key provided by the developer:

```bash
curl -X POST \
  https://your-railway-url.up.railway.app/api/laundry/v1/waterFeedAttachedToTap \
  -F "apiKey=YOUR_TEST_API_KEY" \
  -F "photo=@/path/to/test-image.jpg" \
  -F "projectNumber=TEST-001"
```

**Expected Response:**
```json
{
  "result": "PASS",
  "reason": "Water supply properly connected with no visible leaks",
  "projectNumber": "TEST-001"
}
```

### 5.2 Test the Dashboard

1. Go to your Vercel dashboard URL
2. Login with your admin credentials
3. You should see:
   - ✅ API keys list
   - ✅ Request logs
   - ✅ Statistics

### 5.3 Create Your First API Key

1. In the dashboard, go to **"API Keys"**
2. Click **"Generate New Key"**
3. Give it a name (e.g., "Production Key")
4. Copy the key - you'll give this to your clients!

🎉 **Congratulations!** Your AI Scanity API is now live in production!

---

## 📚 API Documentation

### Authentication

All API requests require an API key provided as a form-data parameter:

```bash
-F "apiKey=sk_your_api_key_here"
```

### Request Format

All endpoints accept `multipart/form-data` POST requests.

**Required Parameters:**
- `apiKey` (string): Your API key for authentication
- `photo` (file): Installation photo (JPG, JPEG, PNG, max 10MB)

**Optional Parameters:**
- `projectNumber` (string): Project identifier (letters, numbers, `_`, `-` only, max 50 chars)
- `twoAxes` (string): Optional parameter for two-axis check

### Response Format

All endpoints return JSON:

```json
{
  "result": "PASS",
  "reason": "Water supply properly connected with no visible leaks",
  "projectNumber": "PROJECT-001"
}
```

**Response Fields:**
- `result` (string): Either `"PASS"` or `"FAIL"`
- `reason` (string): Explanation of the result (max 100 characters)
- `projectNumber` (string): Project identifier (only if provided in request)

### Error Responses

**400 Bad Request:**
```json
{
  "error": "apiKey is required"
}
```

**401 Unauthorized:**
```json
{
  "error": "Invalid API key"
}
```

**405 Method Not Allowed:**
```json
{
  "error": "ONLY POST REQUESTS ARE ALLOWED"
}
```

**500 Internal Server Error:**
```json
{
  "error": "AI analysis failed"
}
```

---

## 🧪 Testing

### Test with cURL

```bash
# Test water feed endpoint
curl -X POST \
  https://your-railway-url.up.railway.app/api/laundry/v1/waterFeedAttachedToTap \
  -F "apiKey=sk_test_your_key_here" \
  -F "photo=@testmap/1aansluitingen/A1.JPG" \
  -F "projectNumber=TEST-001"
```

### Test with k6 (Load Testing)

```bash
# Install k6
brew install k6  # macOS
# or download from https://k6.io/docs/get-started/installation/

# Run test
k6 run testWaterFeed.js
```

### Expected Response

```json
{
  "result": "PASS",
  "reason": "Water supply properly connected with no visible leaks",
  "projectNumber": "TEST-001"
}
```
---

## 🏗️ Architecture

### System Components

```
┌─────────────────────────────────────────────────────────────────┐
│                         CLIENT LAYER                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐          │
│  │  Technician  │  │   Mobile App │  │  Web Client  │          │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘          │
└─────────┼──────────────────┼──────────────────┼─────────────────┘
          │                  │                  │
          │ POST multipart   │                  │
          ↓                  ↓                  ↓
┌─────────────────────────────────────────────────────────────────┐
│                      API GATEWAY LAYER                           │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │              Go API Server (Railway)                      │  │
│  │  • Authentication  • Image processing  • Routing          │  │
│  └────────┬──────────────────────────────┬──────────────────┘  │
└───────────┼──────────────────────────────┼─────────────────────┘
            │                              │
            │ Validate API key             │ AI Analysis
            ↓                              ↓
┌─────────────────────┐        ┌─────────────────────┐
│   Supabase DB       │        │   OpenAI API        │
│  • api_keys         │        │  • GPT-4 Vision     │
│  • requests         │        │  • Image analysis   │
│  • user_profiles    │        │  • PASS/FAIL logic  │
└─────────┬───────────┘        └─────────────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────────────┐
│                      ADMIN DASHBOARD                             │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │           Next.js Dashboard (Vercel)                      │  │
│  │  • User auth  • API key mgmt  • Request monitoring        │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```


---

### Environment Variables

**Railway (Server-side):**
```
OPENAI_API_KEY          → OpenAI API access
SUPABASE_URL            → Database connection
SUPABASE_SERVICE_ROLE_KEY → Full database access (⚠️ secret!)
```

**Vercel (Client-safe):**
```
NEXT_PUBLIC_SUPABASE_URL      → Database connection (safe)
NEXT_PUBLIC_SUPABASE_ANON_KEY → Limited database access (safe)
NEXT_PUBLIC_API_URL           → Go API endpoint
```

---

## 🎯 System Overview

### Architecture

```
┌─────────────┐
│   Client    │
│ (Technician)│
└──────┬──────┘
       │ POST /api/laundry/v1/{endpoint}
       │ (photo + apiKey)
       ↓
┌─────────────────┐
│   Go API Server │ ← Railway
│  (Railway.app)  │
└────────┬────────┘
         │
         ├─→ OpenAI API (image analysis)
         │
         └─→ Supabase (logging)
                ↑
         ┌──────┴──────┐
         │  Dashboard  │ ← Vercel
         │  (Vercel)   │
         └─────────────┘
```

### Components

1. **Go API Server** - Handles photo uploads, AI analysis via OpenAI, quality control decisions
2. **Next.js Dashboard** - Admin interface for managing API keys, viewing requests, and statistics
3. **Supabase Database** - Stores users, API keys, and request logs

### Available Endpoints

| Endpoint | Description |
|----------|-------------|
| `/api/laundry/v1/waterFeedAttachedToTap` | Check water supply connection |
| `/api/laundry/v1/drainHoseInDrain` | Check drain hose placement |
| `/api/laundry/v1/powerCordInSocket` | Check power connection |
| `/api/laundry/v1/rinseCycleMachineIsOn` | Check if machine is powered on |
| `/api/laundry/v1/shippingBoltsRemoved` | Check shipping bolts removal |
| `/api/laundry/v1/levelIndicatorPresent` | Check spirit level presence |

---

**Built with ❤️ for quality control automation**

**Last Updated**: 10-11-2025
**Version**: 1.0.0
