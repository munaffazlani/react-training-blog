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

Reducer is also a Function which will accept two things in the argument. First thing is your initial state. And another thing is all your action functions. 

You will have to pass down the initial state as state = initialState. 

But you will not have to pass any actions, It will listen for all the action by default. You will write a switch and case statements for handling the types of actions you want to handle here. 

\----Code-----

Your reducer is listening to all the actions by default. Than with the switch case statements you are saying that when action.type is "GIVE ME COFEE" do some thing with the state .

When you created your action function, you stored your command in type key, thats why we are using type here,  you can name anything but type is standard.

If you want to access the payload from the action you can just say action.payload. That's how you will change that state. And that will update every where. 



Also you can accept the argument

Just remember one thing Store is a global storage of your data (state) and your data changing methods (setState), so you can access it from anywhere.

Action is a command which will heard by reducer and reducer will than change the value of state.

### Let's Create Global Redux Store

Let's take the easiest part down, creating store and providing it to all the components. 

* producers
* roasters
* importers/exporters
* retailers
* manufacturers
* baristas

For over 30 years, SCAA has been dedicated to creating a vibrant specialty coffee community by recognizing, developing and promoting specialty coffee. SCAA sets and maintains quality standards for the industry, conducts market research, and provides education, training, resources, and business services for its members.

Coffee cupping, or coffee tasting, is the practice of observing the tastes and aromas of brewed coffee. It is a professional practice but can be done informally by anyone or by professionals known as "Q Graders". A standard coffee cupping procedure involves deeply sniffing the coffee, then loudly slurping the coffee so it spreads to the back of the tongue.

The coffee taster attempts to measure aspects of the coffee's taste, specifically the body (the texture or mouthfeel, such as oiliness), sweetness, acidity (a sharp and tangy feeling, like when biting into an orange), flavour (the characters in the cup), and aftertaste. Since coffee beans embody telltale flavours from the region where they were grown, cuppers may attempt to identify the coffee's origin.