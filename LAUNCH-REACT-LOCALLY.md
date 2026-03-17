# How to Launch Your React Webpage Locally

Follow these steps in order. Use **Cursor’s terminal** (View → Terminal) or the **Mac Terminal** app.

---

## Prerequisites

- **Node.js** must be installed. To check, run:
  ```bash
  node --version
  ```
  If you see a version (e.g. `v20.x.x`), you’re good. If not, install from [nodejs.org](https://nodejs.org) (use the LTS version).

---

## Step 1: Create the React + TypeScript project (if you don’t have Webpage1 yet)

In the terminal, go to your Playspace folder and create the project:

```bash
cd /Users/jennynixon/Documents/Playspace
npm create vite@latest Webpage1 -- --template react-ts
```

- If it asks **“Ok to proceed?”** (about installing `create-vite`), type **`y`** and press Enter.
- This creates a **Webpage1** folder with a React + TypeScript app.

---

## Step 2: Go into the project folder

```bash
cd Webpage1
```

You must be inside **Webpage1** for the next steps.

---

## Step 3: Install dependencies

```bash
npm install
```

This downloads the packages React needs (can take a minute). Wait until it finishes with no errors.

---

## Step 4: Start the local dev server

```bash
npm run dev
```

You should see something like:

```
  VITE v5.x.x  ready in xxx ms

  ➜  Local:   http://localhost:5173/
  ➜  press h + enter to show help
```

---

## Step 5: Open the webpage in your browser

1. **Click the link** in the terminal: **http://localhost:5173/**  
   or  
2. Open your browser and go to: **http://localhost:5173/**

You should see the React app (e.g. Vite + React welcome page, or your Hello World if you’ve already changed it).

---

## Step 6: Stop the server when you’re done

In the terminal where the server is running, press:

**`Ctrl + C`**

That stops the dev server. The page will stop loading until you run `npm run dev` again.

---

## Quick reference (after the project exists)

Whenever you want to run the React app again:

```bash
cd /Users/jennynixon/Documents/Playspace/Webpage1
npm run dev
```

Then open **http://localhost:5173/** in your browser.

---

## If something goes wrong

| Problem | What to do |
|--------|------------|
| **`command not found: npm`** | Install Node.js from [nodejs.org](https://nodejs.org). |
| **`EACCES` or permission errors** | Don’t use `sudo`. Make sure you’re in `Playspace` (or `Webpage1`) and try `npm install` again. |
| **Port 5173 already in use** | Another app is using that port. Stop the other app, or Vite will sometimes offer a different port (e.g. 5174)—use the URL it prints. |
| **Blank or broken page** | Hard refresh: `Cmd + Shift + R` (Mac). Check the terminal for red error messages. |
| **Changes don’t show** | Save the file; the dev server usually reloads automatically. If not, refresh the browser. |
