# 🚀 The Ultimate Windows Git & Lazygit Setup

**Zero-frustration, step-by-step configuration for a professional development workflow.**

---

### 🛡️ Pro-Tip: Keep Your Email Private

Before you start, protect your inbox and identity. GitHub allows you to use a **"No-Reply" email address** for commits.

1. Go to your **[GitHub Email Settings](https://github.com/settings/emails)**.
2. Copy your unique `xxxx+username@users.noreply.github.com` address.
3. Use this address in **Step 2** below instead of your personal email.

---

### 1. Install the Essentials

Download and run these installers using the **default settings**.

* **[Download Git for Windows](https://git-scm.com/download/win)**
* *Verification:* Open a terminal and type: `git --version`

---

### 2. Configure Your Identity

Open your terminal (PowerShell) and paste these lines:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@users.noreply.github.com"

```

---

### 3. Secure SSH Setup (No Passwords Required)

Generate a secure key to talk to GitHub without typing your password every time.

**Generate:**

```bash
ssh-keygen -t ed25519 -C "your-email@users.noreply.github.com"

```

*(Press **Enter** through all prompts.)*

**Add to GitHub:**

1. **Copy Key:** `cat $env:USERPROFILE\.ssh\id_ed25519.pub | clip`
2. **Paste:** Go to **[GitHub SSH Settings](https://github.com/settings/ssh/new)**, click **New SSH Key**, and save.

---

### 4. The "Set & Forget" SSH Agent

Ensure your computer remembers your key even after a restart.

1. **Open PowerShell as Administrator.**
2. **Execute:**
```powershell
Set-Service ssh-agent -StartupType Automatic
Start-Service ssh-agent
ssh-add $env:USERPROFILE\.ssh\id_ed25519

```



---

### 5. Install Lazygit

The fastest way to manage your Git workflow.

1. **[Download the latest release](https://github.com/jesseduffield/lazygit/releases)** (look for `..._Windows_x86_64.zip`).
2. **Extract** `lazygit.exe`.
3. **Move** `lazygit.exe` into `C:\Windows` (or a folder in your PATH).
4. **Verification:** Type `lazygit` in your terminal. You are now ready to go!

---

### ⚡ Quick Command Reference

| Goal | Command |
| --- | --- |
| **Check Setup** | `ssh -T git@github.com` |
| **Launch Lazygit** | `lazygit` |
| **Check Identity** | `git config --list` |

---

### 🛠️ Troubleshooting Checklist

* **Terminal acting up?** Download the **[Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)** from the Microsoft Store for a glitch-free experience.
* **Command not found?** Simply restart your terminal window.
* **Permission issues?** Run `ssh-add $env:USERPROFILE\.ssh\id_ed25519` to refresh the agent.

---

*Happy Coding! You're now set up with a professional, secure, and fast Git environment.*
