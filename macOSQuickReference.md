# macOS QuickReference

### install brew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### install pyenv

```
brew install pyenv
```

### install python3.6.5

```
pyenv install 3.6.5
pyenv global 3.6.5
```

### install virtualenvwrapper mac

```
echo 'export PATH="/usr/local/opt/python/libexec/bin:/usr/local/sbin:$PATH"' >> ~/.zshrc
pip install virtualenv
pip install virtualenvwrapper
```
add below lines to `.zshrc`

```
# Configuration for virtualenv
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
source /usr/local/bin/virtualenvwrapper.sh
```
