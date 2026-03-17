# Connect Playspace to GitHub — Step-by-Step Guide

Follow these steps in order. Your folder is already prepared for **Step 4** onward.

---

## What you need before starting

- **A GitHub account.** If you don’t have one: go to [github.com](https://github.com) → Sign up (free).  
  *(If your workplace uses GitHub, you may need to ask someone like Igor for an account or username.)*
- **This folder:** `Playspace` on your Mac.
- **Terminal access:** you can use the terminal in Cursor (or the Mac Terminal app).

---

## Step 1: Create a new repository on GitHub

1. **Log in** to [github.com](https://github.com).
2. **Create a new repo:**
   - Click the **+** icon (top right) → **New repository**  
     — or go directly to: [https://github.com/new](https://github.com/new).
3. **Fill in the form:**
   - **Repository name:** e.g. `Playspace` (or any name you like; no spaces).
   - **Description (optional):** e.g. `Transcripts and learning projects`.
   - **Public** or **Private:** choose what you prefer.
   - **Do not** check “Add a README file”.
   - **Do not** add a .gitignore or license (we already have files in the folder).
4. Click **Create repository**.

After that, GitHub shows a page with setup commands. You’ll use the **repository URL** in Step 5.

---

## Step 2: Copy your repository URL

On the new repo page, GitHub shows something like:

- **HTTPS:** `https://github.com/YOUR_USERNAME/Playspace.git`
- **SSH:** `git@github.com:YOUR_USERNAME/Playspace.git`

**Use the HTTPS URL** (easier if you’re new). Replace `YOUR_USERNAME` with your actual GitHub username.

Example: `https://github.com/jennynixon/Playspace.git`

Keep this URL ready for Step 5.

---

## Step 3: (Optional) Install GitHub CLI for easier login

If you prefer to authenticate from the terminal:

- Install: [https://cli.github.com](https://cli.github.com)  
  or with Homebrew: `brew install gh`
- Then run: `gh auth login` and follow the prompts.

If you skip this, Git will prompt for your GitHub username and password (or a **Personal Access Token**) when you push in Step 6.

---

## Step 4: Open terminal in your project folder

- In **Cursor:** Terminal → New Terminal (or **View → Terminal**).  
  Make sure the shell is in your project folder. If not, run:
  ```bash
  cd /Users/jennynixon/Documents/Playspace
  ```

---

## Step 5: Connect this folder to your GitHub repo

Run these **one at a time**. Replace `YOUR_REPO_URL` with the URL you copied in Step 2 (e.g. `https://github.com/jennynixon/Playspace.git`).

**5a. Add the remote (only once):**
```bash
git remote add origin YOUR_REPO_URL
```
Example:
```bash
git remote add origin https://github.com/jennynixon/Playspace.git
```

**5b. Ensure the main branch is named `main`:**
```bash
git branch -M main
```

**5c. Push your code to GitHub:**
```bash
git push -u origin main
```

- If Git asks for **username:** your GitHub username.
- If it asks for **password:** use a **Personal Access Token**, not your GitHub password.  
  To create one: GitHub → **Settings → Developer settings → Personal access tokens → Tokens (classic)** → Generate new token. Give it a name, check **repo**, then generate and copy the token into the password prompt.

After this, your Playspace files will be on GitHub.

---

## Step 6: Confirm on GitHub

- Refresh your repository page on GitHub. You should see your files (e.g. `Transcripts/`, `GITHUB-SETUP-GUIDE.md`, etc.).

---

## Summary checklist

- [ ] GitHub account ready  
- [ ] New repo created on GitHub (no README / no .gitignore)  
- [ ] Repository URL copied  
- [ ] Terminal open in `/Users/jennynixon/Documents/Playspace`  
- [ ] `git remote add origin YOUR_REPO_URL` run  
- [ ] `git branch -M main` run  
- [ ] `git push -u origin main` run (and login/token if prompted)  
- [ ] Files visible on GitHub  

---

## If something goes wrong

- **“remote origin already exists”**  
  Run: `git remote remove origin`  
  Then run again: `git remote add origin YOUR_REPO_URL`

- **“failed to push” / “permission denied”**  
  Check: correct URL, correct username, and that you’re using a Personal Access Token (not your account password) if using HTTPS.

- **“Repository not found”**  
  Confirm the repo name and username in the URL, and that you’re logged into that GitHub account.

You can delete or keep `GITHUB-SETUP-GUIDE.md` after you’re done; it’s just for this setup.
