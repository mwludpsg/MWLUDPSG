# MWLUDPSG Collaboration Guide

Welcome to the **MWLUDPSG** website project!  

This document explains how to set up secure **SSH access** and collaborate using Git.

1. Repository Information

a, Repo URL: [https://github.com/Wangguanyu-astro/MWLUDPSG]
b, Main Branch: `main`
c, Access Method: SSH (recommended) + Git


2. One-Time SSH Setup

If you already use SSH with GitHub, you can skip this section.

2.1. Generate an SSH Key

Run the following command in your terminal (Git Bash on Windows, Terminal on macOS/Linux):

```
ssh-keygen -t rsa -b 4096 -C "your_github_email@example.com"
```

Press Enter through all prompts to accept the defaults.
Your keys will be created at:

```
~/.ssh/id_rsa      # private key (keep this safe)
~/.ssh/id_rsa.pub  # public key (upload this to GitHub)
```

2.2. Add the Public Key to GitHub

(1) Log in to your GitHub account

(2) Click your profile → Settings

(3) Go to SSH and GPG keys

(4) Click New SSH key

(5) Add a title (e.g., MyLaptop)

(6) Paste your id_rsa.pub contents

(7) Click Add SSH key

2.3. Test the Connection

Run:
```
ssh -T git@github.com
```

If you see a message like this, it’s working:

"Hi <your-username>! You've successfully authenticated, but GitHub does not provide shell access."


3. Clone the Repository

Use the SSH URL, not HTTPS:
```
git clone git@github.com:Wangguanyu-astro/MWLUDPSG.git
cd MWLUDPSG
```


4. Development Workflow

4.1. Pull the latest code
```
git pull
```

4.2. Create your own feature branch (recommended)
```
git checkout -b feature/your-feature-name
```

4.3. Edit and commit your changes
```
git add .
git commit -m "describe your changes"
```

4.4. Push your branch to the remote repository
```
git push -u origin feature/your-feature-name
```

4.5. Open a Pull Request

Go to the GitHub repo page
Click Compare & pull request
Add a short description and submit


5. Common Issues
Q1: I get “Permission denied (publickey)” when pushing

Check:
Your SSH key is added to GitHub
You are using the SSH URL (git@github.com:), not HTTPS
If you cloned via HTTPS, switch to SSH:
```
git remote set-url origin git@github.com:Wangguanyu-astro/MWLUDPSG.git
```


Q2: Some temporary files (like .vs, bin, obj) are showing up in git?
No worries — these are already ignored via the project’s .gitignore file.


6. Contact
For any questions or permission issues, please contact the repository owner:
wangguanyuastro@gmail.com


Thank You for Contributing!
Please keep commits clean and branches well-organized — let’s make this project even better together!!!
