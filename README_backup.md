# reTHINK Hackathon

This Repo is dedicated to help TADHack participants using reTHINK framework for web application development. First, it helps with reTHINK configuration and give some guidelines on how to use it in web applications. Then, a programming challenge is proposed, with several tasks that each participant should accomplish. At the end, is provided a form, which must be filled out by each participant.
 
## 1st Challenge

Each team should develop a web application that uses the X hyperty that can deployed from the `hysmart.rethink.ptinovacao.pt` catalogue. This hyperty generates a code according to the name of your team that should be passed as input. The resulting code should be shown in the developed application.   

##### IMAGE


### Task 1 (`estimation: 45 minutes`)

#### Task 1.1:

`reTHINK distribution files` - To deploy reTHINK runtime in your web application is necessary to execute `rethink.js`. This script can be found in `dev-runtime-browser` repository. There are two ways to obtain this script:

* Add the following dependency into your `package.json` file

```shell
# Add dependency to your package.json file:
  "dependencies": {
    "runtime-browser": "reTHINK-project/dev-runtime-browser#develop"
  },
```

* Clone the repository using the following command and copy the `bin` folder into the root of your application 

```shell
# Clone the runtime-browser repository:
$ git clone --branch=develop https://github.com/reTHINK-project/dev-runtime-browser.git
```

#### Task 1.2:

`Load Runtime` - reTHINK runtime can be obtained after the `rethink.js` execution by your application.

```shell
#Example
rethink.default.install({ 
  domain: runtime_domain,
  development: true,
  runtimeURL: runtimeURL
  }).then((runtime) => {
    ... 
});
```

#### Task 1.2:

`Load an Hyperty` - An Hyperty can be loaded using `requireHyperty()` method. For this challenge should be loaded the `X` Hyperty, which is ready to be used in `hybroker.rethink.ptinovacao.pt` catalogue. To deploy it in a successfull manner, authentication is mandatory.

```shell
#Example
RUNTIME.requireHyperty(hypertyURI(hyperty_domain, 'GroupChatManager')).then((hyperty) => {
  ...
});
```

### Task 2 (`estimation: 45 minutes`)

`Generate a code` - The generated code depends of the name of each team that should be passed as input.

```shell
#Example
XHyperty.generateCode(name).then((code) => {
  ...
});
```

##### Note: Don't forget to display the generated code on your developed application (html page).


## 2nd Challenge



## NVM, Node and NPM Installation

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


## reTHINK environment configuration 

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
```

```shell
# run the toolkit for browser
$ npm run start:browser

# Note: If you are using MAC OS you may need to run the above command with sudo privileges; 
#       Otherwise with Linux, you can solve this problem with following command. 
#       As result, you do not need sudo privileges.

$ sudo setcap 'cap_net_bind_service=+ep' `which node`

```


Open https://catalogue.localhost/ and accept certificate

Open https://localhost/ and select an Hyperty to run.


## reTHINK distribution files 

To deploy reTHINK runtime in your web application is necessary to execute `rethink.js`. This script can be found in `dev-runtime-browser` repository. There are two ways to use this script:

* Add the following dependency into your `package.json` file

```shell
# Add dependency to your package.json file:
  "dependencies": {
    "runtime-browser": "reTHINK-project/dev-runtime-browser#develop"
  },
```

* Clone the repository using the following command and copy the `bin` folder into the root of your application 

```shell
# Clone the runtime-browser repository:
$ git clone --branch=develop https://github.com/reTHINK-project/dev-runtime-browser.git
```


## Usefull documentation

* [Complete espefication](https://github.com/reTHINK-project/specs)

* [GroupChatManager](https://github.com/reTHINK-project/dev-hyperty/tree/develop/docs/group-chat-manager)

* [APP Example](https://github.com/reTHINK-project/dev-app/tree/develop)

* [Webinars](https://www.youtube.com/channel/UC4xTKj2ZvhUyJosA_fLeAhg)

## Challenge

The main goal of this challenge is to develop a Chat web application using the GroupChatManager hyperty. In this application, users can create chat rooms to exchange messages with each other. Each chat room must be identified by a certain name. The ideia is that users can invite others to some specific chat room by indicating their email address. In addition, users can also join some chat room using its identifier. Once inside a chat room, users can exchange messages between them. 
Each user should be authenticated using their preferred Identity Provider (e.g. Google, Microsoft). reTHINK provides an authentication mecanism, so the developer does not have to handle this.

### Task 1 (`estimation 45 minutes`)

`Load Runtime` - reTHINK runtime is obtained after the `rethink.js` execution.

```shell
#Example
rethink.default.install({ 
  domain: runtime_domain,
  development: true,
  runtimeURL: runtimeURL
  }).then((runtime) => {
    ... 
});
```

`Load an Hyperty` - An Hyperty can be loaded using `requireHyperty()` method. For this challenge should be loaded the `GroupChatManager` Hyperty, which is ready to be used in `hybroker.rethink.ptinovacao.pt` catalogue. To deploy it in a successfull manner, authentication is mandatory.

```shell
#Example
RUNTIME.requireHyperty(hypertyURI(hyperty_domain, 'GroupChatManager')).then((hyperty) => {
  ...
});
```

### Task 2 (`estimation 1 hour and 30 minutes`)

`Creation of chat rooms` - Chat rooms must be identified by a certain name. When a chat room is created, the user can also provide a list of emails to invite to the chat room. Alternatively, if some user is at a different domain, this must be provided in order to receive the invitation.

```shell
#Example
GroupChatManager.create(identifier, emails, domains).then(function(chatController) => {
  ...
});
```

### Task 3 (`estimation 45 minutes`)

`Join chat room` - As soon as the chat room is created, is generated a URL (`DataObject Reporter URL`) that other users should use if they want to join the chat room.

```shell
#Example
GroupChatManager.join(url).then(function(chatController) => {
  ...
});
```

### Task 4 (`estimation 45 minutes`)

`Exchange of messages` - Inside the chat room, users can easly exchange messages between them.

```shell
#Example
chatController.send(message).then(function(result) => {
  ...
});
```

### How to succeed and win the prize 

Each participant must complete the proposed challenge, but to win the prize the application will have to stand out from the others.

The criterias that we will consider are the following:

 * Additional Features 
 
 * User Interface
 
 * Code Quality

## Feedback

Your feedback is extremelly important for us in order to improve reTHINK framework in the future. Please fill this [FORM](https://docs.google.com/forms/d/e/1FAIpQLSeFt56Ura0zkTqg_VX9od_jBZtE3-2mt_urTFvxsoRuQ3uJRw/viewform).

##### Note: If you do not fullfill this form, your participation wont be considered! 