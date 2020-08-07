---
templateKey: blog-post
title: "React-Redux With Hooks and Without Hooks :  Complete Practical Guide "
date: 2020-08-07T15:16:21.229Z
description: I hated redux when I started learning it. Just because it has lots
  of boilerplate to understand.  that's why I am making this blog to help you
  love it. As I love it now :)
featuredpost: true
featuredimage: /img/flavor_wheel.jpg
tags:
  - flavor
  - tasting
---
![React Redux Training](/img/flavor_wheel.jpg "React Redux Training")

## What the heck is redux and react-redux

Your application wants to handle lots of data. Lots of places. You know how hectic it can be to just pass down states and state handliing functions from components to components. That's where the redux comes in to the picture. With redux you can create your global data store which you can access that data in to any component. You can also change that data from any component and it will re-render everywhere. Sounds cool! So, grab a cofee and let's get coding. 

First, the difference. For no confusion. 

Redux is the core library.

React-redux is created with redux to connects your redux store with your  react components.

### React-redux has three main parts.

* #### Store
* #### Action
* #### Reducer

### New way of handling state with Actions and Reducers.

You remember how we store the state and state changing function in the component file. Reducer is the same thing. Here you wanna take away state and state changing logic and function from component to it's own .js file. So, later you can access that data from anywhere and also change it with the Action.

### Now, what is action?

Imagine you went to cofee shop and you asked, give me 2 cup cofee, or said would you like to go on a date tonight? This is just a command you gave and according to your command receptionist will respond with something. Here our receptionist is reducer. You will dispatch an Action and that action will be heard by reducer. Reducer holds the state and state changing logics, according to your action it will do update state.

Let's digest this new way of changing state with Action and Reducer. 

### Actions in Code

Action is pretty simple, it's just a pure function which will return an object. 

\----------Code-----------

Here is an example of action, here inside the type I stored my command which is "GIVE ME COFFEE"

Now let's say you wanna pass down how many coffee you want? So, this action can also accept additional things and you can attach those things in your object. Like this.

\---------Code-------------

Now this actions will be heard by reducers. Let's see how?

### What is reducer?

Till now, you were storing state inside the component and it's handler functions also within it. And than pass down those function and state as you need. But with reducer now you will store this state and it's handler function in the different js file. So, later you can connect it to whole application and use it in any component. And change it with the actions we made.\
(I know I repeated my self but this is the core concept)

### Reducer in code

Create a separate folder for reducer, make a simple js file and name it anything.

Reducer is just a Function which will accept two things in the argument. First thing is your initial state. And another thing is all your action functions. 

You will have to pass down the initial state as state = initialState. 

But you will not have to pass any actions, It will listen for all the action by default. You will write a switch and case statements for handling the types of actions you want to handle here. 

\----Code-----

Your reducer is listening to all the actions by default. Than with the switch case statements you are saying that when action.type is "GIVE ME COFEE" do some thing with the state .

When you created your action function, you stored your command in type key, thats why we are using type here,  you can name anything but type is standard.

If you want to access the payload from the action you can just say action.payloadName. That's how you will change that state. And that will update every where. 

Do not forget to export reducer. That will help us to create our store.

\-----------reducers-example-------------

### Still, How to use this ?

Yes! Coming to that. but first let's create the store and pass the state to all components. 

### What is redux Store ?

Just remember one thing redux store is a global storage of your states. Rright now, your reducer is holding your state. which you wanna pass down to all the components. For that you will have to create redux store and provide the store to the whole react app.

First, we will get the createStore function from 'redux'.\
Import our reducer.\
Pass reducer to the createStore to get the redux store ready. \
You can name it anything, I will just keep it store. Like this.

\-------Code Example ------ 

#### Combine Reducer

This is just for the one simple reducers. But inside your big application you will have multiple reducers, for that you will have to import all the reducers and combine that and than pass to create store.

To do that, go inside the reducer folder and make a new js file called : rootReducer.js

You will have to import combineReducer from react-redux. combineReducer will accept an object with all reducers. \
Import all the reducers you have here. and pass it as object value. \
Remember, Whatever you will name your key for reducer here, you will have to use the same name to select it later. So, I will keep it same as it's imported name

Export it.

\-------root reducer--------

Now after combining all the reducers you can import root reducer



Than import provider from 'react-redux' and we will wrap this Provider around our whole app and pass store to it as props. Like this 

\------ full code example -----

Now, we are ready to select our state in any reducer and dispatch actions to change it as well. Let's learn how to do that. Fun begins here.

### How to select redux-store values with Hooks?



### How to dispatch action with Hooks?



### Why you should know both ? 

Because there are so many places where you will find old code with react   16 even. Also you can not use hooks with class based components. 

How to select redux-store values without Hooks

How to dispatch action without Hooks



Here is the cheatsheet

Reducer

combine multiple reducer make root reducer

create store with root reducer and provide it to app.

create action

dispatch action