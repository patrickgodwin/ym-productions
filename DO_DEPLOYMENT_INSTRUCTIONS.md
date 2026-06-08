# Deploy Your Moment Productions to DigitalOcean App Platform

## Status
✅ **GitHub repo is ready:** https://github.com/patrickgodwin/ym-productions
✅ **All files committed** — app.yaml is configured

## Next Steps: Deploy via DigitalOcean Console

### Option 1: Quick Deploy (Web Console) — ~2 minutes

1. Go to [DigitalOcean App Platform](https://cloud.digitalocean.com/apps)
2. Click **Create App**
3. Select **GitHub** as source
4. Authorize GitHub (if needed) and select: `patrickgodwin/ym-productions`
5. Choose branch: `master`
6. Click **Next**
7. **Review App Settings:**
   - Service name: `web` (pre-filled)
   - Source dir: `/` (leave blank = root)
   - Build command: Leave empty
   - Run command: Leave empty
8. Click **Create Resources**
9. Wait for deployment (~2-5 min)
10. Your live URL will appear at the top — **Copy and share!**

### Option 2: Deploy via doctl CLI

If you have doctl installed:

```bash
doctl apps create --spec app.yaml
```

Your app will be assigned a URL like: `https://ym-productions-xxxx.ondigitalocean.app`

## What Happens Next
- DO builds and serves your static HTML/CSS/JS
- Site is live immediately
- Any commits to `master` auto-deploy

## Testing
Once deployed, visit your DO URL and verify:
- ✅ Homepage loads
- ✅ Navigation works
- ✅ Videos/images render
- ✅ Forms submit (if any)

**Need help?** Check DigitalOcean status dashboard or reach out to support.
