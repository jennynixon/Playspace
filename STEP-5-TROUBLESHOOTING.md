# Step 5 Troubleshooting — Connect & Push to GitHub

Your repo is set up: **origin** is `https://github.com/jennynixon/Playspace.git`, and you have commits ready to push. Use this if the **push** step fails.

---

## Run the push (in Cursor’s terminal or Mac Terminal)

Open a terminal, go to your project, and run:

```bash
cd /Users/jennynixon/Documents/Playspace
git push -u origin main
```

---

## If it asks for username and password

GitHub **no longer accepts your account password** for `git push` over HTTPS. You must use a **Personal Access Token (PAT)** as the “password.”

### Create a Personal Access Token

1. **Log in to GitHub** in your browser.
2. Click your **profile picture** (top right) → **Settings**.
3. In the left sidebar, scroll to **Developer settings** → click it.
4. Click **Personal access tokens** → **Tokens (classic)**.
5. Click **Generate new token** → **Generate new token (classic)**.
6. **Note:** e.g. `Playspace push`.
7. **Expiration:** pick what you want (e.g. 90 days or No expiration).
8. **Scopes:** check **repo** (full control of private repositories).
9. Click **Generate token**.
10. **Copy the token immediately** (you won’t see it again). It looks like `ghp_xxxxxxxxxxxx`.

### When Git asks for a password

- **Username:** your GitHub username (e.g. `jennynixon`).
- **Password:** **paste the token** (the `ghp_...` string), not your GitHub account password.

Then run again:

```bash
git push -u origin main
```

---

## Other common errors

### “remote origin already exists”

You’ve already added the remote. Skip `git remote add origin ...` and only run:

```bash
git push -u origin main
```

### “Repository not found” or “Permission denied”

- Confirm the repo exists at: https://github.com/jennynixon/Playspace  
- Confirm you’re logged into that GitHub account.
- If it’s an organization repo, make sure your account has push access.
- Use a new PAT with **repo** scope (see above).

### “Support for password authentication was removed”

You must use a **Personal Access Token** as the password, not your GitHub account password. See “Create a Personal Access Token” above.

### “failed to push some refs” / “Updates were rejected”

If GitHub says the remote has commits you don’t have (e.g. you added a README on the website), run:

```bash
git pull origin main --rebase
git push -u origin main
```

---

## Check that it worked

After a successful push, open:

**https://github.com/jennynixon/Playspace**

You should see your files: `.gitignore`, `GITHUB-SETUP-GUIDE.md`, `Transcripts/`, etc.
