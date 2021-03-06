With React Native, you don't use a special syntax for defining styles. You just style your application using JavaScript.
All of the core components accept a prop named style. The style names and values usually match how CSS works on the web,
except names are written like backgroundColor instead of background-color. 

The style prop can be a plain old JavaScript object. That's the simplest and what we usually use for example code. 
You can also pass an array of styles - the last style in the array has presedence, so you can use this to inherit styles. 

As the component grows in complexity, it is often cleaner to use StyleSheet.create to define several styles in one place.
Here's an example:

                   import React, { Component } from 'React'
                   import { AppRegistry, StyleSheet, Text, View } from 'react-native';
                   
                   class LotsOfStyles extends Component {
                    render() {
                     return (
                      <View>
                       <Text style={styles.red}>just red</Text>
                       <Text style={styles.bigblue}>just bigblue</style>
                       <Text style={[styles.bigblue, styles.red]}>red, then bigblue</red>
                      </View>
                         );
                        }
                      }
                      
                    const styles = StyleSheet.create({
                     bigblue: {
                       color: 'blue',
                       fontWeight: 'bold',
                       fontSize: 30,
                       };
                     red: {
                      color: 'red',
                      },
                    });
                    
                    AppRegistry.registerComponent('LotsOfStyles', ()=> LotsOfStyle);
                    
One common pattern is to make your component accept a style prop whcih in turn is used to style subcomponents. You
can use this to make styles cascade the way they do in CSS.
                     
