# dev-reTHINK-initial-guide

INTRO: This repository provides required commands 

### NVM, Node and NPM Installation

```shell
# NVM Installation
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
# Restart your terminal so NVM can be used

# Node Installation
$ nvm install 6.6.0

# To verify that node and npm was correctly install run:
$ node -v
$ npm -v
```

### reTHINK environment configuration 

```shell
# clone the toolkit repository:
$ git clone --branch=develop https://github.com/reTHINK-project/dev-hyperty-toolkit.git

# clone the dev-hyperty repository:
$ git clone --branch=develop https://github.com/reTHINK-project/dev-hyperty.git

# Note: Ensure that both repositories are cloned inside the same directory 
```

```shell
# Inside the toolkit repository run:
$ npm install -g karma-cli gulp-cli browserify
$ npm install

# Note: It may take a while to install all modules. Hang tight. 
# If you are using Linux, probably you may have some problems running npm run start:browser because you will need the sudo privileges, so, you can solve this problem with this command:

$ sudo setcap 'cap_net_bind_service=+ep' `which node`
```

