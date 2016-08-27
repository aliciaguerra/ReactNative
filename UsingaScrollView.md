#Using a ScrollView
The ScrollView is a generic scrolling container that can host multiple components and views. The scrollable items need
not be homogenous, and you can scroll both vertically and horizonally (by setting the horizontal property).

The example creates a vertical scrollView with both images and text mixed together?

                     import React, { Component } from 'react';
                     import { AppRegistry, ScrollView, Image, Text, View } from 'react-native'
                     
                     class IsScrolledDownAndWhatHappenedNextShockedMe extends Component {
                      render() {
                       return (
                        <ScrollView>
                         <Text style={{fontSize:96}}>Scroll me plz</Text>
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Text style={{fontSize:96}}>If you like</Text>
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Text style={{fontSize:96}}>Scrolling down</Text>
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Text style={{fontSize:96}}>What's the best</Text>
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Text style={{fontSize:96}}>Framework around?</Text>
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Image source={require('./img/favicon.png')} />
                         <Text style={{fontSize:80}}>React Native</Text> 
                        </ScrollView>
                           );
                          }
                        }
                        
                       AppRegistry.registerComponent('IsScrolledDownandWhatHappenedNextShockedMe', () => IsScrolledDownandWhatHapenedNextShockedMe);
                       
ScrollView works best to present a small amount of things of a limited size. All the elements and views of a ScrollView 
are rendered, even if they are not currently shown on screen. 
                     
