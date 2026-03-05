# MSF_Map_Railway

**Railway-specific Metaverse Server** — A deployment-ready fork of the Metaverse spatial fabric map service, configured for one-click deployment on [Railway](https://railway.com). This repository is the source used by the [Metaverse Server Railway template](https://omb.metaverse-standards.org/install/railway).

> This is a **Railway deployment repository**. For contributing code changes, extending features, or understanding the full project architecture, see and fork the main development repository: **[MSF_Map_Svc](https://github.com/MetaversalCorp/MSF_Map_Svc)**.

---

## Overview

MSF_Map_Railway provides:

- **One-click deployment** via Railway's template
- **Node.js Metaverse Server** + **MySQL database** (pre-configured)
- **Pre-initialized schema** and sample project
- **Automatic environment configuration** (HTTPS, SSL, env vars)
- **Scene Assembler** — web-based 3D scene editor for building metaverse spaces from GLB/GLTF models

Part of the [Open Metaverse Browser](https://omb.metaverse-standards.org/) ecosystem.

---

## Installation (Railway)

Follow the official guide: **[Railway Metaverse Server Setup](https://omb.metaverse-standards.org/install/railway)**

### 1. Create Required Accounts

- **GitHub**: [github.com](https://github.com) — create a free account if needed
- **Railway**: [railway.com](https://railway.com) — sign up with GitHub. Free tier includes $5 credit for the first month (sufficient for development and testing)

### 2. Deploy the Metaverse Server Template

1. Deploy the [Metaverse Server Railway template](https://railway.com/template)
2. Authorize GitHub access if prompted
3. On **MVServer**, click **Configure**
4. Set **MVSADMINKEY** — your passkey for private access to the Scene Assembler
5. Set **MYCOMPANYID** — your RP1 Developer Center Company ID (lowercase). Get one at [dev.rp1.com](https://dev.rp1.com)
6. Click **Save Config**, then **Deploy**
7. Wait 2–3 minutes for setup to complete

### 3. Fork This Repository

You must fork MSF_Map_Railway to add objects and files to your server:

1. Visit: [github.com/MetaversalCorp/MSF_Map_Railway](https://github.com/MetaversalCorp/MSF_Map_Railway)
2. Click **Fork**
3. Select your GitHub account

**Optional — clone locally:**

```bash
git clone https://github.com/MetaversalCorp/MSF_Map_Railway.git
cd MSF_Map_Railway
```

### 4. Connect Railway to Your Fork & Redeploy

1. Open your Railway project → select **MVServer**
2. Go to **Settings** → **Source Repo**
3. Click **Change Repo** → select your fork (`your-username/MSF_Map_Railway`)
4. Ensure branch = `main`
5. Click **Deploy** or **Redeploy**
6. Wait for the build to complete

> If deployment fails, check for syntax errors in your MVServer Variables.

### 5. Verify the Server

1. Open **MVServer** → **View Logs** → **Deploy Logs**
2. Look for:
   ```
   SQL Server READY
   Server running on port 8080
   ```

If both appear, your Metaverse Server is operational and ready to attach to the Metaverse Browser.

---

## Scene Assembler (Quick Start)

The Metaverse Server bundles the **Scene Assembler** — a web-based 3D scene editor that lets you build metaverse spaces from GLB/GLTF models, sync them with a JSON representation, and publish scenes to your Fabric. Full documentation: [Scene Assembler](https://omb.metaverse-standards.org/en/tools/scene-assembler).

### Accessing the Scene Assembler

1. Open your server's root URL (e.g. `https://your-metaverse-server.up.railway.app`)
2. Enter your **MVSADMINKEY** when prompted (Fabric URL is pre-filled)
3. Press **Enter** — the Scene Assembler loads with a sample scene

### What You Can Do

- **Add 3D objects** from the library (GLB/GLTF models) into your scene
- **Move, rotate, and scale** objects with the interactive gizmo
- **Edit the scene as JSON** — changes sync both ways
- **Add custom objects:** Upload `.glb` or `.gltf` files to the `/objects` folder in your fork, commit, push — Railway redeploys and new objects appear in the Objects Library

### Publishing Your Scene

1. Click the **Publish** icon in the toolbar
2. Wait for the overlay to complete — your scene is now stored on the server
3. Click the **gear icon** to copy your **Spatial Fabric URL**
4. Use this URL to attach your Fabric via the [RP1 Developer Center](https://dev.rp1.com)

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| W | Move (translate) |
| E | Rotate |
| R | Scale |
| Delete / Backspace | Delete selected |
| Ctrl+Z / Ctrl+Shift+Z | Undo / Redo |
| F | Frame camera on selected |
| Escape | Deselect |

---

## SSL / HTTPS

Railway automatically provides:

- HTTPS
- SSL certificates
- Automatic renewal

No manual SSL configuration is required.

---

## Deploying Changes

Railway redeploys automatically when:

- You push updates to your GitHub fork
- You click **Deploy** manually
- Environment variables change

**To update your server:**

1. Commit changes to your fork
2. Push to GitHub
3. Railway redeploys automatically

---

## Contributing

**This repository is for Railway deployment only.** To contribute code, add features, or fix bugs in the Metaverse Map Service:

1. **Fork the main development repository:** [MSF_Map_Svc](https://github.com/MetaversalCorp/MSF_Map_Svc)
2. Make your changes there
3. Submit pull requests to MSF_Map_Svc

MSF_Map_Svc contains the full project structure, build scripts, database schemas, and Scene Assembler source. Changes accepted there may be synced to this Railway-specific repo for deployment.

---

## Links

- [Railway Metaverse Server Setup](https://omb.metaverse-standards.org/install/railway) — full installation guide
- [Scene Assembler](https://omb.metaverse-standards.org/en/tools/scene-assembler) — full documentation, keyboard shortcuts, troubleshooting
- [MSF_Map_Svc](https://github.com/MetaversalCorp/MSF_Map_Svc) — main development repository
- [Open Metaverse Browser Wiki](https://omb.metaverse-standards.org/)
- [RP1 Developer Portal](https://dev.rp1.com)

---

## License

Apache-2.0. See [LICENSE](LICENSE).
