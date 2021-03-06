# 2nd Challenge

Each team should develop a chat application that uses the `Code Generator` and `Group Chat Manager` hyperties that can deployed from the `hysmart.rethink.ptinovacao.pt` catalogue. The `Code Generator` hyperty generates a code according to the name of your team that should be passed an input. The `Group Chat Manager` hyperty main functionality is to handle text conversations among groups, including:

 * Creation of a new Group Chat with possibility to invite users to join it
 
 * Send message to group

 * Receive message from group with identity from sender
 

With this application, users can create chat rooms to exchange messages with each other. Each chat room must be identified by a certain name. The idea is that users can invite others to some specific chat room by indicating their email address. In addition, users can also join some chat room using its identifier. Once inside a chat room, users can exchange messages between them. 
   

![2nd Challenge](https://github.com/BernardoMG/dev-reTHINK-challenge/blob/master/Figures/2-Challenge.jpg)

To overcome this second challenge, each team should accomplish all the tasks bellow. 
Your feedback is extremely important for us in order to improve reTHINK framework in the future. As such, after complete all the tasks, each team must fill out the page 3 of this [Survey](https://docs.google.com/forms/d/e/1FAIpQLSeFt56Ura0zkTqg_VX9od_jBZtE3-2mt_urTFvxsoRuQ3uJRw/viewform). 

### Note: If you do not fill out this form, your participation wont be considered! 


## Task 1 (`estimation: 15 minutes`)

To accomplish this first task, each team can continue working on the developed application of the first challenge. The only difference is that now the application must use `Code Generator` and `Group Chat Manager` hyperties. So, its necessary to deploy the `Group Chat Manager` hyperty into the application. This second hyperty is also present in the `hysmart.rethink.ptinovacao.pt` catalogue.


## Task 2 (`estimation: 2 hours and 30 minutes`)

### Task 2.1:

`Creation of chat rooms` - Chat rooms must be identified by a certain name. When a chat room is created, the user can also provide a list of emails to invite to the chat room. Alternatively, if some user is at a different domain, this must be provided in order to receive the invitation. 

```shell
#Example
GroupChatManager.create(identifier, emails, domains).then(function(chatController) => {
  ...
});
```


### Task 2.2: 

`Join chat room` - As soon as the chat room is created, is generated a URL (`DataObject Reporter URL`) that other users should use if they want to join the chat room.

```shell
#Example
GroupChatManager.join(url).then(function(chatController) => {
  ...
});
```


### Task 2.3: 

`Exchange of messages` - Inside the chat room, users can easily exchange messages between them.

```shell
#Example
chatController.send(message).then(function(result) => {
  ...
});
```

## Task 3 (`estimation: 15 minutes`)

`Generate a code and broadcast to all the participants` - The generated code depends of the name of each team that should be passed as input. When the code is received should be send to all the participants of the chat room.

##

### [Survey Page 3!!!](https://docs.google.com/forms/d/e/1FAIpQLSeFt56Ura0zkTqg_VX9od_jBZtE3-2mt_urTFvxsoRuQ3uJRw/viewform) 

