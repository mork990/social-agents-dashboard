# 🎭 Social Agents Dashboard

Live dashboard for managing social media agents with AI personas.

## 🚀 Live Demo

**View the dashboard here:** [https://YOUR_USERNAME.github.io/social-agents-dashboard/](https://YOUR_USERNAME.github.io/social-agents-dashboard/)

## 📊 Features

- **Real-time monitoring** of all social agents
- **Live statistics** - posts, followers, engagement
- **Proxy status** for each agent
- **Beautiful UI** with automatic updates
- **Responsive design** - works on all devices

## 🛠️ Setup

### 1. Fork this repository

Click the "Fork" button in the top-right corner.

### 2. Enable GitHub Pages

1. Go to **Settings** → **Pages**
2. Source: Deploy from a branch
3. Branch: `main` → `/root`
4. Click **Save**

Your dashboard will be live at: `https://YOUR_USERNAME.github.io/social-agents-dashboard/`

### 3. Update the data

The dashboard reads from `data/dashboard-data.json`. To update:

```bash
# Generate fresh data
cd /path/to/social-agents-system
node dashboard-server.js generate

# Copy to web/data/
cp dashboard-data.json web/data/

# Commit and push
cd web
git add data/dashboard-data.json
git commit -m "Update dashboard data"
git push
```

## 🔄 Auto-Update (Optional)

Set up automatic data updates using GitHub Actions:

1. Create `.github/workflows/update-data.yml`
2. Add your server SSH key to GitHub Secrets
3. The workflow will pull fresh data every hour

## 📁 File Structure

```
web/
├── index.html              # Main dashboard
├── data/
│   └── dashboard-data.json # Agent data
└── README.md               # This file
```

## 🎨 Customization

### Change colors

Edit the CSS in `index.html`:
- Main gradient: `#667eea` and `#764ba2`
- Card background: `white`
- Text colors: `#2d3748` and `#718096`

### Change update interval

In `index.html`, line ~450:
```javascript
setInterval(loadData, 5000); // Change 5000 to desired milliseconds
```

### API Endpoint

Update the `API_ENDPOINT` variable in `index.html`:
```javascript
const API_ENDPOINT = 'YOUR_GITHUB_RAW_URL/data/dashboard-data.json';
```

## 🔐 Security

- Dashboard is **read-only** - no sensitive data exposed
- All actions require CLI access to the main system
- Proxy details show only host:port (no credentials)

## 📞 Support

For issues or questions, contact the system administrator.

---

**Built with:** HTML, CSS, JavaScript  
**Data format:** JSON  
**Hosting:** GitHub Pages  
**Updates:** Real-time (5s interval)
