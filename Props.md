Most components can be customized when they are created, with different parameters. These creation parameters are called
props. 

For example, one basic React Native component is the Image. When you create an image, you can use a prop named source to
control what image it shows. 

               import React, { Component } from 'react';
               import { AppRegistry, Image } from 'react-native';
               
               class Bananas extends Component {
                render() {
                 let pic = {
                  uri: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Bananavarieties.jpg'
                 };
                 return (
                  <Image source={pic} style={{width: 193, height: 110}}/>
                         );
                        }
                      }
               AppRegistry.registerComponent('Bananas', ()=> Bananas);
               
Notice that {pic} is surrounded by braces, to embed the variable pic into JSX. You can put any JavaScript expression inside
braces in JSX. 

Your own components can also use props. This lets you make a single component that is used in many different places in your 
app, with slighlty different properties in each place. Just refer to this.props in your render function. Here's an example:

               import React, { Component } from 'react';
               import {AppRegistry, Text, View} from 'react-native';
               
               class Greeting extends Component {
                render() {
                 return(
                  <Text>Hello {this.props.name}!</Text>
                     );
                    }
                }
                
                class LotsOfGreetings extends Component {
                 render() {
                  return(
                   <View style={{alignItems: 'center'}}>
                   <Greeting name="Rexxar" />
                   <Greeting name="Jaina" />
                   <Greeting name="Valeera" />
                   </View>
                    );
                  }
                } 
                
                AppRegistry.registerComponent('LotsOfGreetings', () => LotsOfGreetings);
                
Using name as a prop lets us customize the Greeting component, so we can reuse that component for each of our greetings. 
This example also uses the Greeting Component in JSX, just like the built-in components. The power to do this is what makes React
so cool - if you find yourself wishing that you had a different set of UI primitives to work with, you just invent new ones.

The other new thing going on here is the View component. A View is useful as a container for other components, to help
control style and layout.

With props and the basic text, image, and view components, you can build a wide variety of static screens.
                
               
               
                


                      
                  
