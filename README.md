## Steps to bootstrap a new Mac

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.

```zsh
xcode-select --install
```


2. Clone repo into new hidden directory.

```zsh
# ...or use HTTPS and switch remotes later.
git clone https://github.com/tonynguyenit18/my_dotfiles.git ~/my_dotfiles
```


3. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/my_dotfiles/.zshrc ~/.zshrc
ln -s ~/my_dotfiles/.gitconfig ~/.gitconfig
```


4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/my_dotfiles/Brewfile

# ...or move to the directory first.
cd ~/my_dotfiles && brew bundle
```