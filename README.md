# pyEnvConfiguration
### Pre-requisites

- [Homebrew](http://brew.sh)
- [Homebrew-versions tap](https://github.com/Homebrew/homebrew-versions)


### Git and GitHub

3. Generate and add `ssh` keys to GitHub

   https://help.github.com/articles/generating-ssh-keys/


### Python

1. Install `pyenv`

   ```bash
   $ brew install pyenv
   ```

2. Configure `pyenv`

   ```bash
   $ echo 'if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi' >> ~/.bash_profile
   ```

3. Eval `pyenv`

   ```bash
   $ eval "$(pyenv init -)"
   ```

4. Install `python`

   ```bash
   $ pyenv install 2.7.10
   ```

5. Set global `python` version

   ```bash
   $ pyenv global 2.7.10
   ```

6. Install `virtualenv` and `virtualenvwrapper`

   ```bash
   $ pip install virtualenvwrapper  # will automatically install virtualenv
   $ pyenv rehash
   ```

7. Configure `virtualenvwrapper`

   ```bash
   $ echo 'export WORKON_HOME=$HOME/.virtualenvs' >> ~/.bash_profile
   $ echo 'export PROJECT_HOME=$HOME/Projects' >> ~/.bash_profile
   $ echo 'export VIRTUALENVWRAPPER_SCRIPT=$HOME/.pyenv/versions/2.7.10/bin/virtualenvwrapper.sh' >> ~/.bash_profile
   $ echo 'source $VIRTUALENVWRAPPER_SCRIPT' >> ~/.bash_profile
   ```

8. Create `PROJECT_HOME` directory

   ```bash
   $ mkdir -p $HOME/Projects
   ```

9. Enable `virtualenvwrapper`

   ```bash
   $ source $HOME/.pyenv/versions/2.7.10/bin/virtualenvwrapper.sh
   ```

### MySQL

1. Install `mysql`

   ```bash
   $ brew install mysql
   ```

2. Configure `mysql` to start on login

   ```bash
   $ ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
   $ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist  # start mysql
   ```


### Redis

1. Install `redis`

   ```bash
   $ brew install redis
   ```

2. Configure `redis` to start on login

   ```bash
   $ ln -sfv /usr/local/opt/redis/*.plist ~/Library/LaunchAgents
   $ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.redis.plist
   ```
   
   ``` Restart the terminal ```

### Project working copy

1. Create project `virtualenv`

   ```bash
   $ mkproject projectname
   ```

2. Install development requirements

   ```bash
   $ brew install swig304 freetype jpeg libpng
   $ LDFLAGS="-L$(brew --prefix openssl)/lib" CFLAGS="-I$(brew --prefix openssl)/include" SWIG_FEATURES="-cpperraswarn -includeall -I$(brew --prefix openssl)/include" pip install --allow-external bitly-api --allow-unverified bitly-api -r requirements/development.txt
   ```

3. Create local settings file

### Frontend libraries

1. Install `node`

   ```bash
   $ brew install node010
   ```

2. Install `node` packages

   ```bash
   $ npm install
   ```

3. Install frontend libraries

   ```bash
   $ ./manage.py bower_install
   ```


### Shell

1. Install `bash-completion`.

   ```bash
   $ brew install bash-completion
   ```
### Recommended Apps

[Recommended OS X Apps](https://github.com/sectioneleven/yougotagift/wiki/Recommended-Apps#os-x)
