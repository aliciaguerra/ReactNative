Mobile apps rarely just consist of just one screen. As soon as you add a second screen to your app, you will have to take into
consideration how the user will navigate from one screen to another.

You can use navigators to transition between multiple screens. These transitions can be typical side-to-side 
animations between down a master/detail stack, or vertical modal popups.

#Navigator
React Native has several built-in components, but for your first app you will probably want to use the Navigator. It
provides a JavaScript implementation of a navigation stack, so it works on both iOS and Android and is easy to customize.

#Working with Scenes
At this point you should feel comfortable rendering all sorts of components in your app, be it a simple View with Text
inside, or a ScrollView with a list of Images. Together these components make up a scene in your app.

A scene is nothing other than a React component that is typically rendered fullscreen. This is in contrast to a Text,
an Image, or even a custom SpinningBeachball component that is needed to be rendered as part of a screen. You may 
have already used one without realizing it - the "HelloWorldApp", the "FlexDirectionBasics", and the "ListViewBasics"
components covered earlier in the tutorials are all examples of scenes.

For simplicity's sake, let's define a simple scene that displays a bit of text. We will come back to this scene
later as we add navigation to our app. Create a file called "MyScene.js" with the following contents:

                    import React, { Component } from 'react';
                    import { View, Text } from 'react-native';
                    
                    export default class MyScene extends Component {
                     static getdefaultProps() {
                      return {
                       title: 'MyScene'
                       };
                      }
                      
                      render() {
                       return (
                        <View>
                         <Text>Hi! My name is {this.props.title}.</Text>
                        </View>
                           )
                          }
                        }
                        
Notice that the export default in front of the component declaration. This will export the component, and in turn
allow other components to import it later on, like so:

                     import React, { Component } from 'react';
                     import { AppRegistry } from 'react-native';
                     
                     import MyScene from './MyScene';
                     
                     class YoDawgApp extends Component {
                      render() {
                       return (
                        <MyScene />
                           )
                          }
                        }
                        
                    AppRegistry.registerComponent('YoDawgComponent', () => YoDawgComponent);
                    
#Using Navigator
Enough about the scenes, let's start navigating. We will start by rendering a Navigator, and then let the Navigator
render the scene for you by by passing your own render function to its renderScene prop.

                     render() {
                      return (
                       <Navigator
                        initialRoute={{ title: 'My Initial Scene', index: 0}}
                        renderScene={{route,navigator}} => {
                         return <MyScene title={route.title} />
                         }}
                         />
                        );
                      ]
                      
Something you will encounter a lot when dealing with navigation is the concept of routes. A route is an object that 
contains information about a scene. It is used to provide all the context that the neighbor's renderScene function needs to
render a scene. It can have any number of keys to help you distinguish your scene, and I hoped to pick a single title key
for the above example.

#Pushing Scenes into the Stack
In order to transition to a new scene, you will need to learn about push and pop. These two methods are provided by the
navigator object that is passed to your renderScene function above. They can be used, as you may have realized, to push
or pop routes into your navigation stack. 

                     navigator.push({
                      title: 'Next Scene',
                      index: 1,
                      });
                      
                     navigator.pop();
                     
A more complete example that demonstrates the pushing and popping of routes could therefore look something like this:

                     import React, { Component, PropTypes } from 'react';
                     import { Navigator, Text, TouchableHighlight, View } from 'react-native';
                     
                     export default class SimpleNavigationApp extends Component {
                      render() {
                       return (
                        <Navigator
                          initialRoute={{ title: 'My Initial Source', index: 0 }}
                          renderScene={(route, navigator) =>
                           return(
                            <MyScene
                             title={route.title}
                             
                             //Function to call when a new scene should be displayed
                             onForward={ ()=> {
                             const nextIndex = route.index + 1;
                             navigator.push({
                             title: 'Scene' + nextIndex,
                             index: nextIndex,
                                 });
                             }}
                             
                             //Function to call to go back to the previous scene
                             onBack={() => {
                              if(route.index>0) {
                               navigator.pop();
                                               }
                                             }}
                                           />
                                          )
                                         }
                                      />
                                     )
                                    }
                                   }
                      
                             class MyScene extends Component {
                              static propTypes = {
                               title: PropTypes.string.isRequired,
                               onForward: PropTypes.func.isRequired,
                               onBack: PropTypes.func.isRequired,
                               }
                               
                              render() {
                               return (
                               <View>
                               <Text>Current Scene: { this.props.title }</Text>
                               <TouchableHighlight onPress={this.props.onForward}>
                                <Text>Tap me to load the next scene</Text>
                               </TouchableHighlight>
                               <TouchableHighlight onPress={this.props.onBack}>
                                <Text>Tap me to go back</Text>
                               </TouchableHighlight>
                               </View>
                                      )
                                    }
                                  }
                                  
In this example, the MyScene component is passed the title of the current route via the title prop. It displays
two tapable components that call onForward and onBack functions passed through its props, which in turn will call
navigator.push() and navigator.pop() as needed.
