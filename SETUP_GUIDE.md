# LinkedIn CDP — Setup Guide

Step-by-step setup for people who have never used a terminal before. Takes about 10 minutes.

---

## What you'll get

An AI assistant that searches LinkedIn for candidates on your behalf. You describe who you're looking for in plain language, and it browses LinkedIn, reviews profiles, collects information, and can send personalized connection requests -- all while behaving like a regular human user.

---

## Step 1 — Sign up for Claude

1. Go to https://claude.ai
2. Create an account (or sign in if you already have one)
3. Choose the **Pro** plan ($20/month) -- this is enough to get started. You can upgrade to Max ($100/month) later if you need more capacity.

---

## Step 2 — Open the terminal

The terminal is a program where you type commands instead of clicking buttons. Don't worry -- you'll only need to copy-paste a few lines.

**Mac:**
- Press `Cmd + Space` (Spotlight search)
- Type `Terminal`
- Press `Enter`

A window with a dark or light background and a blinking cursor will open. That's the terminal.

**Windows:**
- Press `Win + X`
- Choose **"PowerShell"** (or "Terminal")

Use PowerShell for all commands below -- regular cmd may not work.

---

## Step 3 — Install Claude Code

Copy the command for your system, paste it into the terminal, and press `Enter`:

**Mac / Linux:**
```
curl -fsSL https://claude.ai/install.sh | sh
```

**Windows (PowerShell):**
```
npm install -g @anthropic-ai/claude-code
```
(If `npm` is not found, first install Node.js from https://nodejs.org — download and click "Next" a few times)

Wait until you see a message that installation is complete.

**Important:** After installation, close the terminal and open it again (same way as Step 2). This is needed so the terminal recognizes the new `claude` command.

---

## Step 4 — Create a working folder

In the terminal, paste and run:

**Mac / Linux:**
```
mkdir -p ~/linkedin-sourcing && cd ~/linkedin-sourcing
```

**Windows (PowerShell):**
```
mkdir -Force ~\linkedin-sourcing; cd ~\linkedin-sourcing
```

This creates a folder called `linkedin-sourcing` in your home directory and moves into it.

---

## Step 5 — Download the configuration file

This file tells the AI assistant how to use the LinkedIn tool, what safety rules to follow, and where everything is located.

**Mac / Linux:**
```
curl -fsSL https://raw.githubusercontent.com/anthroos/linkedin-cdp-open/main/CLAUDE.md -o CLAUDE.md
```

**Windows (PowerShell):**
```
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/anthroos/linkedin-cdp-open/main/CLAUDE.md" -OutFile "CLAUDE.md"
```

---

## Step 6 — Launch Claude Code

In the same terminal, type:

```
claude
```

The first time you run it, a browser window will open asking you to sign in. Use the same Claude account from Step 1. After signing in, come back to the terminal -- it's ready.

---

## Step 7 — Start sourcing

Now you're inside Claude Code. Just paste one of these example prompts and press `Enter`:

**Example 1 -- Simple search:**
```
Find me Senior React developers in Kyiv with 3+ years of experience
```

**Example 2 -- Detailed search:**
```
I'm looking for a Product Manager with fintech experience in Berlin or remote. Ideally 5+ years in product, worked with payment systems or banking. Show me their profiles.
```

**Example 3 -- Search + connect:**
```
Search for DevOps engineers in Poland who work with Kubernetes. For the best matches, send a connection request with a short personalized note mentioning their current role.
```

The AI will handle the rest: install dependencies, launch Chrome, calibrate the screen, search LinkedIn, and show you results.

---

## Troubleshooting

**"command not found: claude"**
Close the terminal and open it again. If it still doesn't work, try running the install command from Step 3 again.

**"command not found: curl"**
On Windows, use PowerShell instead of cmd: press `Win + X`, choose "PowerShell".

**Chrome doesn't open**
Make sure Google Chrome is installed. Download it from https://www.google.com/chrome/ if needed.

**LinkedIn asks for captcha**
Stop the current task (press `Ctrl + C`), solve the captcha in the Chrome window manually, then restart Claude Code.

**Rate limit reached**
The tool has built-in safety limits to protect your LinkedIn account. If it says the daily limit is reached, just continue tomorrow.

---

## Daily usage (after setup)

After the first-time setup, your daily workflow is just two commands:

```
cd ~/linkedin-sourcing
claude
```

Then describe what you need. The AI remembers how everything works from the CLAUDE.md file.

---

## Need help?

If anything doesn't work, reach out -- happy to jump on a 15-minute call and set it up together.
