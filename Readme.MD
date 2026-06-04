# 💍 Wedding Gallery

A beautiful, cinematic wedding gallery website that displays your wedding **videos** and **photos** directly from Google Drive — accessible to anyone via a public URL. No API key needed.

---

## 📁 Project Files

```
wedding-gallery/
├── index.html   ← The website (do not edit)
├── config.js    ← Your configuration — edit this only
└── README.md    ← This guide
```

---

## ✏️ Step 1 — Edit `config.js`

Open `config.js` in any text editor (Notepad, VS Code, etc.) and fill in your details.

### 1A — Couple's Info

```js
brideName:    "Priya",
groomName:    "Rahul",
weddingDate:  "12 March 2025",
weddingVenue: "Grand Hall, Bhubaneswar",
```

---

### 1B — Add Your 3 Videos

Do this for **each** of your 3 video files:

1. Go to your Google Drive folder
2. Right-click the video → **Share**
3. Under **General access** → select **"Anyone with the link"** → set to **Viewer** → click **Done**
4. Click **Copy link**
5. Paste the link into the `videos: [ ]` section in config.js

```js
videos: [
  {
    link: "https://drive.google.com/file/d/YOUR_VIDEO_1_ID/view?usp=sharing",
    name: "Wedding Ceremony"
  },
  {
    link: "https://drive.google.com/file/d/YOUR_VIDEO_2_ID/view?usp=sharing",
    name: "Reception"
  },
  {
    link: "https://drive.google.com/file/d/YOUR_VIDEO_3_ID/view?usp=sharing",
    name: "Highlights Reel"
  },
],
```

---

### 1C — Add Your Photos

Same process — right-click each photo → Share → Copy link → paste below.
Add as many as you want by copying the `{ link, name }` block.

```js
photos: [
  {
    link: "https://drive.google.com/file/d/YOUR_PHOTO_1_ID/view?usp=sharing",
    name: "Bride & Groom"
  },
  {
    link: "https://drive.google.com/file/d/YOUR_PHOTO_2_ID/view?usp=sharing",
    name: "The Ceremony"
  },
  {
    link: "https://drive.google.com/file/d/YOUR_PHOTO_3_ID/view?usp=sharing",
    name: "Family Portrait"
  },
  // Add more below this line...
],
```

> ⚠️ **IMPORTANT:** You must share EACH file individually — sharing only the
> folder is NOT enough. Right-click each file → Share → "Anyone with the link".

---

## 🐙 Step 2 — Push to GitHub

Pick one of the two options below.

---

### ✅ Option A — GitHub Website Upload (Easiest — no Git needed)

**1. Create a GitHub account** (if you don't have one)
→ Go to [https://github.com](https://github.com) → Sign up

**2. Create a new repository**
- Click the **"+"** icon (top right) → **"New repository"**
- Repository name: `wedding-gallery`
- Visibility: ✅ **Public**
- Leave everything else as default
- Click **"Create repository"**

**3. Upload your files**
- On the next screen, click **"uploading an existing file"**
- Drag and drop all 3 files:
  - `index.html`
  - `config.js`
  - `README.md`
- Scroll down → click **"Commit changes"**

✅ Done! Your files are now on GitHub.

---

### ⚙️ Option B — Git Commands (Terminal / Command Prompt)

**Prerequisites:** Install Git from [https://git-scm.com](https://git-scm.com)

---

**Step 1 — Open Terminal**
- **Windows:** Search "Command Prompt" or "Git Bash" in Start menu
- **Mac:** Press `Cmd + Space` → type "Terminal" → Enter

---

**Step 2 — Go to your project folder**
```bash
cd path/to/wedding-gallery
```
> Example Windows: `cd C:\Users\Sagar\Downloads\wedding-gallery`
> Example Mac/Linux: `cd ~/Downloads/wedding-gallery`

---

**Step 3 — Set up Git and push**

Run these commands one by one:

```bash
# Initialize Git in the folder
git init

# Stage all 3 files
git add .

# Save a snapshot with a message
git commit -m "Initial wedding gallery"

# Rename the branch to main
git branch -M main

# Connect to your GitHub repo (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/wedding-gallery.git

# Push files to GitHub
git push -u origin main
```

> When asked for a password, do NOT use your GitHub password.
> Instead, create a **Personal Access Token**:
> GitHub → Profile icon → Settings → Developer settings
> → Personal access tokens → Tokens (classic) → Generate new token
> → Check ✅ `repo` → Generate → **Copy that token and paste as the password**

---

**Step 4 — Updating files in the future**

Whenever you change `config.js` (add more photos/videos):

```bash
git add config.js
git commit -m "Added new photos"
git push
```

The live site updates automatically within ~1 minute.

---

## 🚀 Step 3 — Deploy on GitHub Pages

After your files are on GitHub, make the site publicly accessible:

**1.** Open your repo on GitHub:
```
https://github.com/YOUR_USERNAME/wedding-gallery
```

**2.** Click the **"Settings"** tab at the top of the repo

**3.** In the left sidebar → scroll down → click **"Pages"**

**4.** Under **"Build and deployment"**, set:

| Field | Value |
|-------|-------|
| Source | `Deploy from a branch` |
| Branch | `main` |
| Folder | `/ (root)` |

**5.** Click **"Save"**

**6.** Wait **1–2 minutes**, then refresh the page

**7.** A green banner appears with your live URL:
```
https://YOUR_USERNAME.github.io/wedding-gallery/
```

**8.** 🎉 Share this URL with family and friends!
Anyone can open it on any device — phone, tablet, laptop — with no login required.

---

## 🔁 Updating the Live Site Later

To add more videos or photos after deployment:

1. Edit `config.js` — paste new Drive links
2. Push to GitHub using Option A (re-upload file) or Option B (`git push`)
3. GitHub Pages rebuilds automatically — live within ~1 minute

---

## 🗺️ Visual Summary

```
Your PC                GitHub                  Internet
─────────────────────────────────────────────────────────

config.js  ──git push──►  wedding-gallery repo
index.html                       │
README.md                        │ GitHub Pages
                                 ▼
                    https://username.github.io/wedding-gallery/
                                 │
                    Anyone with the URL can view ✅
```

---

## ❓ Frequently Asked Questions

**Q: Video shows a black screen when I click it?**
The video file must be individually shared as "Anyone with the link — Viewer". Sharing only the folder is not enough.

**Q: Photos show a broken image icon?**
Same reason — each photo needs its own share setting. Right-click → Share → "Anyone with the link".

**Q: How do I find a file's ID in the link?**
Your link looks like this:
```
https://drive.google.com/file/d/  1AbCdEfGhIjKlMnOpQr  /view?usp=sharing
                                  ↑ this is the File ID ↑
```

**Q: I updated config.js but the website didn't change?**
- Make sure you pushed the updated file to GitHub
- Try a hard refresh: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)

**Q: Can I add more than 3 videos?**
Yes! Just add more entries inside `videos: [ ]` in config.js:
```js
{ link: "https://drive.google.com/file/d/YOUR_ID/view", name: "Video Name" },
```

**Q: Can I change the website URL?**
The URL is `https://YOUR_USERNAME.github.io/REPO_NAME/`.
- To change the repo name: GitHub → Settings → General → rename it
- To use a custom domain (e.g. `www.rahulpriya.com`): GitHub → Settings → Pages → Custom domain

**Q: Is there a file size limit for Drive videos?**
Google Drive's free tier gives 15 GB storage. Wedding videos are typically
1–4 GB each, so 3 videos should be well within the free limit.

---

*Share the link — keep the memories forever* 💛