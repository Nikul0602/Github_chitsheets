 ---

# GitHub Multi-Account SSH Setup (Personal + Work)

This guide explains how to configure **two GitHub accounts on the same machine** using SSH keys.

* Personal GitHub → `personal` SSH key
* Work GitHub → `work` SSH key

No credential switching required.

---

# 1. Go to SSH Directory

```bash
cd ~/.ssh
ls
```

Typical location:

```
C:\Users\<username>\.ssh
```

---

# 2. Remove Old Keys (Optional Reset)

```bash
Remove-Item id_ed25519
Remove-Item id_ed25519.pub
```

Verify:

```bash
ls ~/.ssh
```

---

# 3. Generate Personal SSH Key

```bash
ssh-keygen -t ed25519 -C "your-personal-email@example.com"
```

Save as:

```
C:\Users\<username>\.ssh\personal
```

Result:

```
personal
personal.pub
```

---

# 4. Generate Work SSH Key

```bash
ssh-keygen -t ed25519 -C "your-work-email@company.com"
```

Save as:

```
C:\Users\<username>\.ssh\work
```

Result:

```
work
work.pub
```

---

# 5. Add Keys to GitHub

Copy keys:

### Personal key

```bash
Get-Content ~/.ssh/personal.pub
```

### Work key

```bash
Get-Content ~/.ssh/work.pub
```

Add them to GitHub:

```
GitHub → Settings → SSH and GPG keys → New SSH key
```

---

# 6. Configure SSH

Create SSH config file:

```bash
notepad ~/.ssh/config
```

Add:

```
# Personal GitHub
Host github-personal
  HostName github.com
  User git
  IdentityFile "C:\Users\<username>\.ssh\personal"
  IdentitiesOnly yes

# Work GitHub
Host github-work
  HostName github.com
  User git
  IdentityFile "C:\Users\<username>\.ssh\work"
  IdentitiesOnly yes
```

---

# 7. Test SSH Authentication

### Test Personal Account

```bash
ssh -T git@github-personal
```

Expected:

```
Hi <personal-username>! You've successfully authenticated.
```

---

### Test Work Account

```bash
ssh -T git@github-work
```

Expected:

```
Hi <work-username>! You've successfully authenticated.
```

---

# 8. Clone Repositories

### Personal repository

```bash
git clone git@github-personal:<username>/<repo>.git
```

Example:

```bash
git clone git@github-personal:Nikul0602/Agentic-AI_with_Langgraph.git
```

---

### Work repository

```bash
git clone git@github-work:<org>/<repo>.git
```

Example:

```bash
git clone git@github-work:Nikulriot/calculator.git
```

---

# 9. Update Existing Repositories

If a repo was cloned earlier:

### Personal repo

```bash
git remote set-url origin git@github-personal:<username>/<repo>.git
```

### Work repo

```bash
git remote set-url origin git@github-work:<org>/<repo>.git
```

Verify:

```bash
git remote -v
```

---

# 10. Push Code

```bash
git push -u origin main
```

---

# 11. Verify Commit Identity

Check last commit:

```bash
git log -1
```

Example output:

```
Author: Nikul Prajapati <nikul@riot-solutions.com>
```

Show only email:

```bash
git log -1 --pretty=format:"%ae"
```

---

# 12. Set Email Per Repository

### Personal repo

```bash
git config user.name "Nikul Prajapati"
git config user.email "<your_personal_email>"
```

### Work repo

```bash
git config user.email "<your_company_email>"
```

---

# 13. Check Git Configuration

Show current repo email:

```bash
git config user.email
```

Show all configuration sources:

```bash
git config --list --show-origin
```

---

# 14. SSH Debugging

If SSH fails:

```bash
ssh -vT git@github-personal
```

or

```bash
ssh -vT git@github-work
```

---

# 15. Expected `.ssh` Folder Structure

```
~/.ssh
│
├── config
├── personal
├── personal.pub
├── work
├── work.pub
├── known_hosts
```

---

# Final Workflow

| Repository Type | Clone URL                                   |
| --------------- | ------------------------------------------- |
| Personal        | `git@github-personal:<username>/<repo>.git` |
| Work            | `git@github-work:<org>/<repo>.git`          |

No credential conflicts.

---

# Optional Tips

### Check current remote

```bash
git remote -v
```

### Show active commit author

```bash
git log -1 --pretty=format:"%an <%ae>"
```

---

# Troubleshooting

### Permission denied (publickey)

Check SSH config:

```
~/.ssh/config
```

Ensure correct key path.

---

### SSH config ignored

Make sure file name is:

```
config
```

NOT:

```
config.txt
```

---

