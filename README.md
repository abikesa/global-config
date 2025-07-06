To fix the incorrect Git username/email showing up in your VS Code commits, you need to check and update your Git configuration. Here's how:

---

### 🔍 1. **Check Current Git User Config**

Open your terminal in VS Code and run:

```bash
git config --global user.name
git config --global user.email
```

Also check the local repo settings (if you're in a project folder):

```bash
git config user.name
git config user.email
```

> If the **local config** is different from what you expect, that will override the global one.

---

### ✏️ 2. **Update Git User Info**

#### 🔄 For all repos (global):

```bash
git config --global user.name "Your Correct Name"
git config --global user.email "you@example.com"
```

#### 🔄 For current repo only:

```bash
git config user.name "Your Correct Name"
git config user.email "you@example.com"
```

---

### ✅ 3. **Check the Fix**

Make a new commit and check with:

```bash
git log -1
```

It should now reflect the correct name/email.

---

### 🧠 Bonus: Use Account-Specific Git Settings

If you want each VS Code project to use a **different identity** (e.g., personal vs company GitHub accounts):

#### 🛠️ Set up a `.gitconfig` include per folder:

1. In your global `~/.gitconfig`, add:

```ini
[includeIf "gitdir:~/path/to/your/project/"]
    path = ~/.gitconfig-work
```

2. Create `~/.gitconfig-work` with:

```ini
[user]
    name = "Work Name"
    email = "work@example.com"
```

---

Let me know if you also need to configure **SSH keys** for multiple accounts — that's often the next step.
