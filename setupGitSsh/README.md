


# 🧑‍💻 Git & SSH Setup in Termux – Clean & Secure Workflow

## 📌 What is this?

This guide walks you through a clean and secure setup of Git and SSH inside **Termux**, allowing you to:

- Commit and push code **without entering your GitHub token every time**
- Use **SSH authentication** instead of HTTPS
- Restart from scratch (perfect for tutorials or fresh installs)
- Avoid exposing your GitHub token in your code or config files

Whether you're creating a video or resetting your dev environment, this documentation gives you all the commands and explanations you need.

---

## ⚙️ Setup Commands + Explanations

### 🧹 1. Reset all previous Git & SSH configuration

```bash
rm -rf ~/.ssh           
# Delete SSH keys and known hosts
rm ~/.gitconfig         
# Delete global Git config (name, email, etc.)
rm -rf .git             
# Optional: reset Git in a specific project


---

🧑‍💻 2. Set your Git identity

git config --global user.name "Your Name"
git config --global user.email "your@email.com"

These values will appear in every Git commit.


---

🔐 3. Generate a new SSH key

ssh-keygen -t ed25519 -C "your@email.com"

When asked for a file path, press Enter to accept the default.

When asked for a passphrase, press Enter to skip (optional).



---

📋 4. Copy your public SSH key

cat ~/.ssh/id_ed25519.pub

Copy the entire output.

Then go to https://github.com/settings/keys
Click "New SSH key", give it a name (ex: Termux), and paste your key.


---

✅ 5. Test the connection

ssh -T git@github.com

You should see:

Hi your-username! You've successfully authenticated, but GitHub does not provide shell access.

That means SSH is correctly configured.


---

🚀 6. Push your code without a token

Instead of cloning via HTTPS:

git clone git@github.com:your-username/your-repo.git

Now you can:

git add .
git commit -m "Your message"
git push origin main

No token or password needed anymore 🔥


---

📣 Want to Learn More?

Check out the full tutorial on YouTube, with step-by-step visuals: 👉 https://youtube.com/@Terminux



Made with 💻 on Termux by @Terminux


