# GitHub Setup Guide
> Repository: EMBEDDED | Author: jit2eapen

---

## STEP 1 — Create GitHub Repository

1. Go to [https://github.com](https://github.com)
2. Click **+** → **New repository**
3. Fill in:

```
Repository name : EMBEDDED
Description     : ESP32 IoT Projects
Visibility      : Public
Initialize      : Leave ALL boxes UNTICKED
```

4. Click **Create repository**

---

## STEP 2 — Create Personal Access Token

1. Go to [https://github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Fill in:

```
Note       : ESP32
Expiration : 90 days
```

4. Tick ✅ **repo** checkbox
5. Click **Generate token**
6. Copy the token immediately:

```
ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

> ⚠️ Save it — you will NEVER see it again!

---

## STEP 3 — Ubuntu PC Setup

Install Git:

```bash
sudo apt install git -y
```

Configure your identity:

```bash
git config --global user.name "jit2eapen"
```

```bash
git config --global user.email "jit2vakathanam@gmail.com"
```

Save credentials (never type token again):

```bash
git config --global credential.helper store
```

---

## STEP 4 — Push Project to GitHub

```bash
cd ~/Documents/PlatformIO/Projects/EP32_LED_CONTROLLER
```

```bash
git init
```

```bash
git add .
```

```bash
git commit -m "ESP32 LED Controller - Initial commit"
```

```bash
git branch -M main
```

```bash
git remote add origin https://github.com/jit2eapen/EMBEDDED.git
```

```bash
git push -u origin main
```

When asked:

```
Username: jit2eapen
Password: ghp_yourtoken
```

---

## STEP 5 — Verify on GitHub

```
https://github.com/jit2eapen/EMBEDDED
```

---

## STEP 6 — Clone on Another PC

```bash
sudo apt install git -y
```

```bash
git clone https://github.com/jit2eapen/EMBEDDED.git
```

```bash
cd EMBEDDED
```

---

## STEP 7 — Add New Project to Same Repo

```bash
cd ~/Documents/PlatformIO/Projects/EP32_LED_CONTROLLER
```

```bash
mkdir -p NEW_PROJECT_NAME/src
```

```bash
git add .
```

```bash
git commit -m "Added new project: NEW_PROJECT_NAME"
```

```bash
git push
```

---

## STEP 8 — Update Code Every Time

```bash
git add .
```

```bash
git commit -m "describe what you changed"
```

```bash
git push
```

---

## Useful Git Commands

| Command | What it does |
|---------|-------------|
| `git status` | Show changed files |
| `git log --oneline` | Show commit history |
| `git add .` | Stage all changes |
| `git push` | Upload to GitHub |
| `git pull` | Download latest from GitHub |
| `git clone <url>` | Download repo to new PC |

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `Permission denied` | Generate new token at github.com/settings/tokens |
| `rejected — fetch first` | Run `git pull --rebase origin main` then push |
| `remote already exists` | Run `git remote set-url origin https://github.com/jit2eapen/EMBEDDED.git` |
| `token expired` | Generate new token at github.com/settings/tokens |
| `push asks password always` | Run `git config --global credential.helper store` |

---

*jit2eapen — Ubuntu 24.04 — EMBEDDED repo*
