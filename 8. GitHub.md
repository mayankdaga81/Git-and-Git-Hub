# 🌐 GitHub – Quick Revision Notes

---

# 🔹 Git vs GitHub

- **Git** = Software (Distributed Version Control System)
- **GitHub** = Cloud-based service to host Git repositories online

GitHub provides:
- Collaboration
- Backup
- Open Source sharing
- Pull Requests (PR)
- Issues tracking
- GitHub Actions (CI/CD)
- Access control

---

# 🔐 Authentication with GitHub

⚠️ Important Update:

GitHub no longer supports password-based authentication for pushing code over HTTPS.

You must use:
- ✅ SSH Keys (Recommended)
OR
- ✅ Personal Access Token (PAT) over HTTPS

---

# 🔑 Setup SSH (Recommended)

### Step 1 – Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### Step 2 – Add SSH key to GitHub

- Copy public key from:
  ```
  ~/.ssh/id_ed25519.pub
  ```
- Go to GitHub → Settings → SSH and GPG keys → Add new key

### Step 3 – Test Connection

```bash
ssh -T git@github.com
```

If successful → You are connected.

---

# 🔗 Check Remote Repository

### 🔹 `git remote -v`

If no remote:

```
(no output)
```

If remote exists:

```
origin  https://github.com/username/repo.git (fetch)
origin  https://github.com/username/repo.git (push)
```

- `origin` = Default remote name
- Fetch = Used when pulling
- Push = Used when pushing

---

# ➕ Add Remote Repository

If no remote exists:

```bash
git remote add <name> <URL>
```

Example:

```bash
git remote add origin https://github.com/username/repo.git
```

👉 `origin` is conventionally used as the name.

---

# ❌ Remove Remote

```bash
git remote remove <name>
```

Example:

```bash
git remote remove origin
```

Used when changing repository.

---

# 🚀 Push Code to GitHub

### Basic Push

```bash
git push <remote> <branch>
```

Example:

```bash
git push origin main
```

---

# 🔥 Set Upstream Branch

First time push:

```bash
git push -u origin main
```

OR

```bash
git push --set-upstream origin main
```

- `-u` is shortcut for `--set-upstream`
- Sets tracking relationship
- After this, you can simply run:

```bash
git push
```

---

# 🔄 Git Fetch vs Git Pull

## 🔹 `git fetch`

- Downloads changes from remote.
- Does NOT merge into your working directory.
- Safe to inspect changes first.

## 🔹 `git pull`

- Fetches + merges automatically.
- Updates your working directory.
- Equivalent to:

```
git fetch + git merge
```

Example:

```bash
git pull origin main
```

- Gets latest code from remote `main`
- Merges into your current branch

---

# 📥 Clone an Existing Repository

### Step 1 – Copy HTTPS or SSH URL from GitHub

### Step 2 – Run:

```bash
git clone <URL>
```

Example:

```bash
git clone https://github.com/username/repo.git
```

- Creates local copy.
- Automatically sets remote as `origin`.

---

# 🧠 Important Interview Points

- GitHub removed password authentication.
- Use SSH or Personal Access Token.
- `origin` is just a name (can be changed).
- `git fetch` is safer than `git pull`.
- `-u` sets upstream tracking.
- Cloning automatically sets remote.
- Never push secrets (.env) to GitHub.

---

# 🔥 Basic GitHub Workflow

```
git add .
git commit -m "message"
git push
```

---

💡 GitHub = Collaboration + Backup + Hosting for Git repositories.
