# Streamlit Cloud Deployment Guide

This guide will help you deploy the Fitness Center Assistant to Streamlit Cloud.

## Prerequisites

1. A GitHub account
2. Your code pushed to a GitHub repository
3. A Streamlit Cloud account (free at https://share.streamlit.io)

## Deployment Steps

### 1. Push Your Code to GitHub

If you haven't already, create a GitHub repository and push your code:

```bash
git init
git add .
git commit -m "Initial commit - Fitness Center Assistant"
git branch -M main
git remote add origin <your-github-repo-url>
git push -u origin main
```

### 2. Deploy to Streamlit Cloud

1. Go to https://share.streamlit.io
2. Sign in with your GitHub account
3. Click "New app"
4. Select your repository: `fitness_center_assistant`
5. Set the **Main file path** to: `src/app.py`
6. Click "Deploy!"

### 3. Configuration

The app is already configured with:
- ✅ `requirements.txt` - All dependencies listed
- ✅ `.streamlit/config.toml` - Theme and server settings
- ✅ Proper file paths for assets

### 4. After Deployment

Once deployed, your app will be available at:
`https://<your-app-name>.streamlit.app`

## File Structure for Deployment

```
fitness_center_assistant/
├── .streamlit/
│   └── config.toml          # Streamlit configuration
├── assets/
│   └── UOP-Logo.jpg         # Logo file
├── src/
│   ├── app.py               # Main Streamlit app
│   ├── data.py
│   ├── theme.py
│   └── logic/
│       ├── attendance.py
│       ├── export.py
│       ├── messaging.py
│       ├── pricing.py
│       └── schedule.py
├── requirements.txt         # Python dependencies
└── README.md
```

## Important Notes

- The app uses relative paths, so it will work on Streamlit Cloud
- Session state is stored in memory (resets on app restart)
- The logo will display if `UOP-Logo.jpg` is in the `assets/` folder
- All dependencies are specified in `requirements.txt`

## Troubleshooting

### App won't start
- Check that `src/app.py` is set as the main file path
- Verify all dependencies in `requirements.txt` are correct
- Check the logs in Streamlit Cloud dashboard

### Logo not showing
- Ensure `UOP-Logo.jpg` is committed to the repository
- Check that the file is in the `assets/` folder

### Import errors
- Make sure all Python files in `src/` are committed
- Verify the `src/` directory structure is correct

## Updating Your App

After making changes:
1. Push changes to GitHub
2. Streamlit Cloud will automatically redeploy
3. Check the deployment status in your Streamlit Cloud dashboard

