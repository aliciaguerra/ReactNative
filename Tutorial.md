#Tutorial
React Native is like React, but it uses native components instead of web components as building blocks. So to understand
the basic structure of the React Native app, you need to understand some of the Native React concepts, like JSX, 
components, state, and props. If you already know React, you still need to know some React-Native specific stuff like
the native components. This tutorial is aimed at all audiences, whether you have React experience or not.

#Hello World
In accordance with the Native tradition of the people, we must first build an app that does nothing except "Hello World".
Here it is:

              import React, { Component } from 'react';
              import { AppRegistry, Text } from 'react-native';
              
              class HelloWorldMap extends Component {
               render() {
                return (
                 <Text>Hello World!</Text>
                 );
                 }
                }
                
                AppRegistry.registerComponent('HelloWorldApp', () => HelloWorldApp);
                
#What's going on here?
Some of the things in here may not look like JavaScript to you. Don't panic. This is the future. 

First of all, ES6 is a set of improvements to JavaScript that is now part of the official standard, but not yet
supported on all browsers, so often it isn't used yet in web development. React Native ships with ES6 support, so you
can use this stuff without worrying about compatibility. import, from, class, extends, and the ()=> syntax in the example 
are all ES2015 features. If you aren't familiar with ES6, you can probably pick it up by reading this code like this
tutorial has. 

The other unusual thing in this code example is <Text>Hello World!</Text>. This is JSX, a syntax for embedding XML
within JavaScript. Many frameworks use a special templating language which lets you embed code inside markup language.
In React, this is reversed. JSX lets you write markup code in JavaScript code. It looks like HTML on the web, except
instead of web things like <div> or <span> , you use React components. In this case, <Text> is a built-in component that
displays some text.

#Component & AppRegistry
So, this code is definiting HellowWorldMap, a new Component and it's registering it with the AppRegistry. When you're
building a React Native app, you'll be making new components a lot. Anything you see on the screen is some sort of
component. A component can be pretty simple - the only thing that's required is a render function which returns some
JSX to render. 

The AppRegistry just tells React Native which component is the root one for the whole application. You won't be thinking
about AppRegistry a lot - there will probably be just one call to AppRegistry.register component in your whole app. It's
included in these examples so you can paste the whole thing into your index.ios.js or index.android.js file and get it running.
