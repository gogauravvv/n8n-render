# **n8n-render README**

Successfully deploy n8n on Render using Docker with the latest configurations and best practices.

## Quick Start
1. Fork this repository or use it as a template
2. Open your Render Dashboard and use this repo as a Blueprint
3. Update the `WEBHOOK_URL` environment variable in `render.yaml` to your domain
4. Deploy and enjoy!

## Important Notes
- **Do not change the storage volume mount path** (`/home/node/.n8n`) - this is hardcoded in n8n
- The `.env` file contains examples that can be added manually as Environment Variables in Render
- Always set the `WEBHOOK_URL` to your actual domain to avoid localhost issues
- Uses the latest n8n Docker image with automatic updates

## What's Updated (2025)
- ✅ Updated to use current Render database plans (flexible pricing)
- ✅ Added required `WEBHOOK_URL` environment variable
- ✅ Updated database instance types to current options
- ✅ Improved documentation and setup instructions
- ✅ Compatible with latest n8n versions (1.94.1+)

## Environment Variables
The following variables should be configured in your Render dashboard:
- `WEBHOOK_URL` - Your n8n domain (e.g., `https://your-app.onrender.com/`)
- `N8N_ENCRYPTION_KEY` - Generate a secure random string
- Database connection variables are auto-populated by Render

## Troubleshooting
- If webhooks aren't working, ensure `WEBHOOK_URL` is set to your actual domain
- For data persistence issues, verify the mount path is exactly `/home/node/.n8n`
- Check Render logs for any startup issues
