# Create alias to automate the process of creating a new project and push it to GitHub.

```bash

# Set the default editor to Visual Studio Code
git config --global core.editor "code --wait"

# Open the global configuration file in Visual Studio Code
git config --global --edit

# Set the default directory to store the projects
# git config --global --add safe.directory "<REPLACE_PATH>"

# Get last 10 repositories created
git config --global alias.ghlc '!gh repo list rodrigozx --json name,createdAt --jq ". | sort_by(.createdAt) | reverse | .[:10] | .[].name"'
# Get 10 repositories
git config --global alias.ghl '!gh repo list --limit 10'

# Create a new public repository on GitHub
git config --global alias.ghcreate '!gh repo create --public --source=. --push'
# Create a new private repository on GitHub
git config --global alias.ghcreatep '!gh repo create --private --source=. --push'
# Initialize and create a new public repository on GitHub
git config --global alias.ghcreateall '!f() { dir=${1:-.}; mkdir -p $dir && cd $dir && echo "#New Proyect by rodrigozx">README.MD && git config --global --add safe.directory $(pwd) && git init && git add . && git commit -m "Initial commit" && git ghcreate;echo Run: cd $dir; }; f'
# Initialize and create a new private repository on GitHub
git config --global alias.ghcreateallp '!f() { dir=${1:-.}; mkdir -p $dir && cd $dir && echo "#New Proyect by rodrigozx">README.MD && git config --global --add safe.directory $(pwd) && git init && git add . && git commit -m "Initial commit" && git ghcreatep;echo Run: cd $dir; }; f'

```
