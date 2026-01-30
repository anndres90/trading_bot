# Deployment Setup Instructions

## CRITICAL: Required Action

The GitHub repository is currently missing essential project files. The deployment to Render will fail until these files are pushed.

## Required Files to Push

You need to push the following files from your local project directory to GitHub:

- `main.py` - Main trading bot application
- `dashboard.py` - Streamlit dashboard
- `requirements.txt` - Python dependencies
- Any CSV data files (e.g., training data)
- Any other project modules and scripts

## How to Push Your Files to GitHub

### Option 1: Using Git Command Line (Recommended)

1. Open PowerShell or Command Prompt
2. Navigate to your project directory:
   ```
   cd C:\Users\anndr\OneDrive\Documentos2\trading_bot
   ```

3. Initialize Git (if not already done):
   ```
   git init
   git add .
   git commit -m "Add trading bot project files"
   ```

4. Add the remote and push:
   ```
   git remote add origin https://github.com/anndres90/trading_bot.git
   git branch -M main
   git push -u origin main
   ```

   If you have a GitHub PAT token, use it as the password when prompted.

### Option 2: Using GitHub Desktop

1. Open GitHub Desktop
2. Click "File" > "Clone Repository"
3. Select your trading_bot repository
4. Make changes and commit them
5. Push to main branch

## Render Deployment

Once files are pushed to GitHub:

1. Render will automatically detect the changes
2. A new deployment will start automatically
3. Check the Render dashboard for deployment status
4. The web service will be available at: https://trading-bot-s8zd.onrender.com
5. The background worker can be deployed for continuous bot operation

## Background Worker Configuration

A background worker has been configured with:
- **Name**: trading_bot  
- **Start Command**: `python main.py`
- **Build Command**: `pip install -r requirements.txt`
- **Language**: Python 3
- **Instance**: Starter (free)

This will run your trading bot continuously on Render's servers.
