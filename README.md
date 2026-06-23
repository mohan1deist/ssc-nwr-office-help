# SSC (NWR) Office Help – Leave Manager

A modern web application for managing leave records of SSC (NWR) officers/officials.

## Roles

| Role | Password (default) | Permissions |
|------|-------------------|-------------|
| Admin | `ssc@nwr` (changeable in Settings) | Full control: add/edit/delete employees, add/edit/delete leaves, settings, Google Sheets sync |
| Editor | `edit@nwr` (changeable in Settings) | Can add new leave entries only. Cannot edit/delete employees or existing leaves. |
| Viewer | *(no password)* | Read-only access to employees and summaries. |

## Make it live using GitHub

### Option 1: GitHub Pages (free)

1. **Create a GitHub repository** and push this project to it.
2. Go to **Settings → Pages** in your repo.
3. Under **Build and deployment**, select **GitHub Actions**.
4. The included `.github/workflows/deploy.yml` will automatically build and deploy the site on every push to `main`.
5. Your site will be available at `https://<your-username>.github.io/<repo-name>/`.

> If you use a custom domain, edit `.github/workflows/deploy.yml` and set `VITE_BASE: '/'`.

### Option 2: Vercel (also free)

1. Push the project to GitHub.
2. Go to [vercel.com](https://vercel.com), sign in, and click **Add New Project**.
3. Import your GitHub repository.
4. Keep the default settings (framework preset: Vite) and click **Deploy**.
5. Vercel will give you a live URL and auto-deploy on every push.

## Google Sheets Backend Setup

1. Create a new Google Sheet.
2. Go to **Extensions → Apps Script**.
3. Replace the default code with the contents of `public/apps-script/Code.gs`.
4. Click **Deploy → New deployment**.
5. Choose type **Web app**, set **Execute as: Me**, and **Access: Anyone**.
6. Copy the web app URL.
7. In the live app, log in as **Admin** and go to **Settings**.
8. Paste the URL, enable Google Sheets sync, and click **Save Settings**.
9. Data will now be stored in your Google Sheet and auto-synced every 5 minutes.

## Local Development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```
