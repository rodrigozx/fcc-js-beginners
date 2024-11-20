# Create alias to automate the process of creating a new project and push it to GitHub.

```bash
git config --global alias.ghcreate '!gh repo create --public --source=. --push'
git config --global alias.ghcreatep '!gh repo create --private --source=. --push'
```
