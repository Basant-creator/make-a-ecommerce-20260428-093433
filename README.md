# Amazon Clone

> 

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js&logoColor=white) ![Express](https://img.shields.io/badge/Express-4.x-000000?logo=express) ![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb&logoColor=white) ![License](https://img.shields.io/badge/license-MIT-blue)

**Project type:** Web Project

Make a E-commerce website for shopping with tech gadget stuff and furniture and groceries

> 👋 **New to coding?** Don't worry — this README walks you through every step in plain English.
> You don't need to understand how everything works under the hood.
> Just follow the numbered steps and you'll have this project running in minutes.

---

## What Does This Project Do?

This is a **full-stack web application** — it has two parts:

- **Frontend** (what users see): HTML, CSS, and JavaScript pages that run in the browser.
- **Backend** (the engine): A Node.js server that handles logins, stores data, and responds to requests from the frontend.

- **Database**: MongoDB Atlas — a cloud database where all user data is securely stored.

Think of it like a restaurant: the frontend is the dining room customers see, the backend is the kitchen, and the database is the pantry.

### How it works

When a user fills in the sign-up form, the browser sends the data to the Node.js server. The server hashes the password (turns it into a scrambled string so it can never be read), saves the user to MongoDB, and replies with a **JWT token** — a small encrypted ticket that proves the user is logged in. Every future request from the browser includes that ticket.

---

## Technologies Used

Here is every tool this project uses, and a plain-English explanation of what each one does.

| Technology | What it does |
|------------|-------------|
| **HTML5** | The skeleton of every page — defines headings, buttons, forms, images, etc. |
| **CSS3** | Controls how everything looks: colours, fonts, spacing, animations, and responsive layout. |
| **JavaScript** | Makes the pages interactive — handles button clicks, form submissions, and API calls. |
| **Node.js** | Runs JavaScript on the *server* (your backend). Handles incoming requests from the browser. |
| **Express 4** | A lightweight framework on top of Node.js that makes it easy to define routes (URLs the server responds to). |
| **MongoDB Atlas** | A cloud database. Stores all your data (users, posts, etc.) online so it persists between restarts. |
| **Mongoose** | A helper library that lets you define the shape of your data and interact with MongoDB using simple JavaScript. |
| **bcryptjs** | Hashes (scrambles) passwords before storing them so they can never be read, even by the server owner. |
| **JSON Web Tokens (JWT)** | Creates a small encrypted 'ticket' that proves a user is logged in, included with every protected request. |
| **dotenv** | Reads secret values (API keys, passwords) from a `.env` file so they are never written in the code. |

---

## What's Inside This Repository?

Here is every file that was generated, and a plain-English explanation of what each one does.
You don't need to edit most of these — but it's good to know where things live.

```
  cart.html**
  checkout.html**
  index.html**
  login.html**
  product-detail.html**
  products.html**
  signup.html**
```

### File descriptions

| File | What it does |
|------|-------------|
| `cart.html**` | A supporting project file. |
| `checkout.html**` | A supporting project file. |
| `index.html**` | A supporting project file. |
| `login.html**` | A supporting project file. |
| `product-detail.html**` | A supporting project file. |
| `products.html**` | A supporting project file. |
| `signup.html**` | A supporting project file. |

---

## Running This Project on Your Computer

### What you need before you start

| Requirement | Why you need it | Where to get it |
|-------------|-----------------|----------------|
| **Node.js 18+** | Runs the backend server on your computer | [nodejs.org](https://nodejs.org) — click **LTS** |
| **A MongoDB Atlas account** | Free cloud database to store user data | [cloud.mongodb.com](https://cloud.mongodb.com) — sign up free |
| **Git** | Downloads the project from GitHub to your computer | [git-scm.com](https://git-scm.com) |

---

### Step 1 — Download the project

```bash
# Downloads all project files from GitHub to your computer
git clone <YOUR_REPO_URL>

# Moves your terminal into the downloaded folder
cd <repo-folder>
```

### Step 2 — Install the project's libraries

```bash
# Reads package.json and downloads all the required Node.js packages.
# This creates a 'node_modules' folder — it may take a minute.
npm install
```

### Step 3 — Set up your secret configuration file

The project needs a file called `.env` that holds sensitive values (database password, secret keys).
This file is **never uploaded to GitHub** — you create it yourself on your own machine.

```bash
# Copies the .env.example template to a new file called .env

# On Windows:
copy .env.example .env

# On Mac / Linux:
cp .env.example .env
```

Now open the `.env` file in any text editor and fill in your values.
See the **Secret Configuration** section below for step-by-step instructions on getting each value.

### Step 4 — Start the server

```bash
# Starts the Node.js backend server
npm start
```

Open your browser and go to **http://localhost:5000**

> **What is localhost:5000?**
> `localhost` means 'this computer'. `5000` is the port the server listens on.
> It's like a private website that only works on your machine while the server is running.

> **Important:** Keep this terminal window open while you're working.
> Closing it stops the server and the website will stop loading.

---

## Secret Configuration (the `.env` file)

### What is a `.env` file?

A `.env` file is a plain text file that stores **secret values** your app needs to run —
things like database passwords and security keys.
It lives in your project folder but is **never uploaded to GitHub**
(the `.gitignore` file automatically excludes it).

Think of it like a keychain: your code knows *that* a key exists,
but the actual key value is only ever on your own machine (or your hosting provider's secure settings).

> ⚠️ **Never share your `.env` file.**
> Do not paste its contents into a chat, email, or GitHub issue.
> Anyone with these values could access your database and all user data.

### Creating your `.env` file

A template called `.env.example` is already in the repository.
It shows all the keys you need, without any real values filled in.

```bash
# Step 1: Copy the template to create your own .env file

# On Windows:
copy .env.example .env

# On Mac / Linux:
cp .env.example .env

# Step 2: Open .env in any text editor and fill in your real values
```

Once filled in, your `.env` file will look something like this:

```env
PORT=5000
MONGO_URI=mongodb+srv://youruser:yourpassword@cluster0.abcde.mongodb.net/myapp?retryWrites=true&w=majority
JWT_SECRET=a_long_random_string_goes_here_never_share_this
```

See the **How to Get Your Secret Values** section below for exact instructions on generating each value.

---

## How to Get Your Secret Values

Follow these steps to generate every value your `.env` file needs.

### `MONGO_URI` — Your Database Connection String

MongoDB Atlas is a free cloud database. `MONGO_URI` is the web address your app
uses to connect to it — think of it as the database's full URL with your username and password baked in.

**Step-by-step:**

1. Go to [https://cloud.mongodb.com](https://cloud.mongodb.com) and create a free account (or sign in).
2. Click **New Project**, give it any name, and click **Create Project**.
3. Click **Build a Database** → choose **M0 FREE** (the free tier) → click **Create**.
4. You will be asked to create a database user:
   - **Username:** choose any username (e.g. `admin`)
   - **Password:** choose a strong password and **write it down** — you'll need it shortly
   - Click **Create User**
5. Under **Where would you like to connect from?** → click **Add My Current IP Address**, then **Finish and Close**.
6. On the dashboard, click **Connect** next to your cluster.
7. Choose **Drivers** from the connection options.
8. You will see a connection string that looks like this:
   ```
   mongodb+srv://admin:<password>@cluster0.abcde.mongodb.net/?retryWrites=true&w=majority
   ```
9. Make two changes to that string:
   - Replace `<password>` with the actual password you chose in step 4.
   - Replace `/?` with `/myapp?` (this sets the database name — change `myapp` to anything you like).
10. The finished string should look like:
    ```
    mongodb+srv://admin:MyPassword123@cluster0.abcde.mongodb.net/myapp?retryWrites=true&w=majority
    ```
11. Copy this full string and paste it as `MONGO_URI=` in your `.env` file.

> **Forgot the string?** Go back to Atlas → your cluster → **Connect** → **Drivers** and it will show it again.

### `JWT_SECRET` — Your Login Security Key

When a user logs in, the server creates a 'login token' — a small encrypted string
that proves the user is who they say they are. `JWT_SECRET` is the secret key used to
create and verify that token. If someone gets hold of this key, they can impersonate any user.

**Rules:**
- It must be a long, random string (at least 32 characters, ideally 64+).
- Never reuse the same secret across different projects.
- Never share it publicly.

**Generate one now — pick any option:**

**Option A — in your terminal (if you have Node.js):**
```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

**Option B — in your terminal (if you have Python):**
```bash
python -c "import secrets; print(secrets.token_hex(64))"
```

**Option C — online (no terminal needed):**
Go to [https://generate-secret.vercel.app/64](https://generate-secret.vercel.app/64) — it generates one instantly.

Copy the output and paste it into your `.env` file like this:
```env
JWT_SECRET=a3f9e2b1c84d7f0e6a5b2c9d1e4f7a0b3c6d9e2f5a8b1c4d7e0f3a6b9c2d5e8
```
(Your value will be different — that is expected.)

### `PORT` — The Server Port Number

This controls which port the server listens on when running locally.

- **When running on your computer:** Set it to `5000`. Your site will be at `http://localhost:5000`.
- **When deployed on Render / Railway / Heroku:** Do **not** set this yourself.
  The hosting platform assigns the port automatically. If you hardcode it, the deployment will fail.

```env
PORT=5000
```

---

## Putting Your Site Online (Deployment)

Once you are happy with the site locally, you can publish it to the internet for free.

### Option 1 — Render (easiest, recommended — free tier available)

Render is a free cloud hosting platform that runs Node.js apps.

1. Your code is already on GitHub ✓
2. Go to [https://render.com](https://render.com) and sign in with your GitHub account.
3. Click **New +** → **Web Service**.
4. Click **Connect** next to this repository.
5. Fill in the following settings:

   | Field | What to enter |
   |-------|--------------|
   | **Name** | Any name you like |
   | **Environment** | `Node` |
   | **Branch** | `main` |
   | **Root Directory** | Leave blank |
   | **Build Command** | `npm install` |
   | **Start Command** | `npm start` |

6. Scroll down to the **Environment Variables** section and add your secrets:

   | Key | Value |
   |-----|-------|
   | `MONGO_URI` | Your full MongoDB Atlas connection string |
   | `JWT_SECRET` | Your generated secret key |

   > **Do NOT add `PORT`** — Render injects this automatically. Adding it yourself will break the app.

7. Click **Create Web Service**.
8. Render builds and deploys your app — this takes 2–5 minutes the first time.
9. Once done, your app is live at `https://<service-name>.onrender.com`.

> 💤 **Free tier note:**
> On the free plan, Render pauses your service after 15 minutes of no visitors.
> The first request after a pause takes about 30 seconds to wake up — this is normal.
> To keep it awake 24/7, use [UptimeRobot](https://uptimerobot.com) (free) to ping your site every 10 minutes.

---

### Option 2 — Railway (alternative)

1. Go to [https://railway.app](https://railway.app) → **New Project** → **Deploy from GitHub Repo**.
2. Select this repository.
3. Click the **Variables** tab and add `MONGO_URI` and `JWT_SECRET`.
4. Railway automatically detects Node.js and deploys. No extra configuration needed.

---

### Common deployment problems and fixes

| Problem | Likely cause | Fix |
|---------|-------------|-----|
| Site loads but login does not work | `MONGO_URI` is wrong or missing | Double-check the Atlas connection string in the Render environment variables panel |
| `Cannot find module` error in logs | Packages were not installed | Make sure your Build Command is set to `npm install` |
| App crashes immediately on startup | A required env variable is missing | Check the Render logs — it will tell you exactly which variable is missing |
| `Error: listen EADDRINUSE` | Port conflict | Remove the `PORT` environment variable from Render — let it set it automatically |

---

## Customising the Look & Feel

You don't need to understand all the code to make this site your own.
Here are the most common things people change, and exactly where to find them.

> 💡 **Fastest way to rename the brand:**
> In VS Code, press **Ctrl + Shift + H** (Windows) or **Cmd + Shift + H** (Mac)
> to open Find & Replace across all files. Search for `Amazon Clone` and replace it with your brand name everywhere at once.

### Colours

Open `style.css` and look for the `:root` block near the top of the file:
```css
:root {
  --primary-color: #ffffff;   /* Main brand colour — buttons, links, highlights */
  --secondary-color: #a0a0a0;  /* Accent colour — hover states, borders */
}
```
Change the hex values to any colour you want. Pick colours at [coolors.co](https://coolors.co).

### Text content

| What to change | File to open | What to look for in that file |
|----------------|-------------|------------------------------|
| Company name (`Amazon Clone`) | All `.html` files | Use Find & Replace to update it everywhere |
| Hero headline | `public/index.html` | The `<h1>` tag inside the section with class `.hero` |
| Hero subheading / description | `public/index.html` | The `<p>` tag directly beneath the `<h1>` |
| Navigation menu links | All `.html` files | The `<nav>` tag → the `<ul>` list items inside it |
| Footer text and links | All `.html` files | The `<footer>` tag at the bottom of each page |
| Browser tab title | All `.html` files | The `<title>` tag inside `<head>` at the top |

### Fonts

Open `style.css` and find `font-family` on the `body` selector.
To switch to a Google Font, add this `@import` at the very top of the CSS file:
```css
/* Add this at the very top of the CSS file (before everything else) */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

body {
  font-family: 'Inter', sans-serif;  /* Replace 'Inter' with your chosen font */
}
```
Browse free fonts at [fonts.google.com](https://fonts.google.com) and copy the `@import` link they provide.

### Images

Open `public/index.html` and look for `<img src="...">` tags.
Replace the `src` value with a link to your own image or a local file path.
For background images defined in CSS, open `style.css` and search for `background-image`.

### How long users stay logged in

By default, users are automatically logged out after **7 days**.
To change this, open `backend/routes/auth.js` and find this line:
```javascript
jwt.sign(payload, process.env.JWT_SECRET, { expiresIn: '7d' })
```
Change `'7d'` to `'1d'` (1 day), `'30d'` (30 days), `'1h'` (1 hour), etc.

---

---

*This project was generated on 2026-04-28 by **AI Website Generator**.*

If you get stuck, re-read the relevant section above carefully — every step is explained in plain English.
For further help, open an issue on the GitHub repository.