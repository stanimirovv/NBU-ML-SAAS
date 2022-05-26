### Get the appropriate Python version
Get python 3.8.
It is inevitable that at some point you will need to have multiple versions of Python installed.

The easiest 'industry standard' way is to use pyenv.
You can read how to set it up here:
```
https://realpython.com/intro-to-pyenv/#using-the-pyenv-installer
```

The gist is:
```
$ curl https://pyenv.run | bash

Then follow the message: 

WARNING: seems you still have not added 'pyenv' to the load path.

Load pyenv automatically by adding
the following to ~/.bashrc:

export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"

Finally:
$ exec "$SHELL" # Or just restart your terminal
```

To verify it works, in your shell you should see ```pyenv```.

Once it is installed, install Python 3.8:
```
pyenv install 3.8.3
```

If you get errors, you are likely missing the dependencies to install python.
The command bellow will improve your chances you can install python (ubuntu/debian):
```
sudo apt update
sudo apt install \
    build-essential \
    curl \
    libbz2-dev \
    libffi-dev \
    liblzma-dev \
    libncursesw5-dev \
    libreadline-dev \
    libsqlite3-dev \
    libssl-dev \
    libxml2-dev \
    libxmlsec1-dev \
    llvm \
    make \
    tk-dev \
    wget \
    xz-utils \
    zlib1g-dev
```

Set your default version to 3.8.0
```
pyenv global 3.8.0
```

### Verification

Depending on your operating system:
```
python3 --version
python --version
```
Should output python 3.8.0