# Multi account Git Repositories

### 1. Generate multiple SSH keys (one per account)
```
# Personal key
ssh-keygen -t ed25519 -C "your.personal@email.com" -f "$HOME/.ssh/id_ed25519_personal"

# Office key
ssh-keygen -t ed25519 -C "your.office@email.com"   -f "$HOME/.ssh/id_ed25519_office"
```

### 2. Add the public keys to GitHub account -> SSH keys

### 3. Create ~/.ssh/config

```
# Personal GitHub
Host github-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal
    IdentitiesOnly yes

# Office GitHub
Host github-office
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_office
    IdentitiesOnly yes
```

### 4. Clone repos with the correct host alias
```
# Personal repo
git clone git@github-personal:your-username/personal-repo.git
cd personal-repo

# Office repo
git clone git@github-office:company/team-repo.git
cd team-repo
```

### 5. Set per-repo Git identity (run once inside each repo)
```
# Inside personal repo
git config user.name "Your Personal Name"
git config user.email "your.personal@email.com"

# Inside office repo
git config user.name "Your Office Name"
git config user.email "your.office@email.com"
```

### Add the Alias to Existing Repos
Open Git Bash (or PowerShell) inside your existing repo and run one of the following:
```
For Personal repo
Bashgit remote set-url origin git@github-personal:your-username/your-repo-name.git
Replace your-username and your-repo-name with actual values.

For Office repo
Bashgit remote set-url origin git@github-office:company-org/team-repo.git
Replace company-org and team-repo accordingly.
```
### Verify it worked
```
git remote -v
```
