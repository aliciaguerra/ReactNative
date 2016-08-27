A component's height and width determine its size on the screen.

#Fixed Dimensions
The simplest way to set its dimensions of a component is by adding a fixed width and height to style. All dimensions in
React Native are unitless, and represent density-independent pixels.

                    import React, { Component } from 'react';
                    import { AppRegistry, View } from 'react-native';
                    
                    class FixedDimensionsBasics extends Component {
                     render() {
                      return (
                       <View>
                        <View style="{{width: 50, height: 50, backgroundColor: 'powderblue'}}" />
                        <View style="{{width: 100, height: 100, backgroundColor: 'skyblue'}}" />
                        <View dtyle="{{width: 150, height: 150, backgroundColor: 'steelblue'}}" />
                       </View>
                         );
                        }
                       ;
                       
                     AppRegistry.registerComponent('AwesomeProject', () => FixedDimensionsBasics);
                     
Setting dimensions this way is common for components that should always render at exactly the same size, regardless of screen 
dimensions. 

#Flex Dimensions
Use flex in a component's style to have the component expand and shrink dynamically based on available space. Normally
you will use flex:1, which tells a component to fill all available space, shared evenly amongst each other component
as the same parent. The larger the flex given, the higher the ratio of space a component will take compared to its 
siblings. 

A component can only expand to fill available space if its parent has dimensions greater than 0. If a parent does not 
have either a fixed width and height or flex, the parent will have dimensions of 0 and the flex dimensions will not be
visible.

                    import React, { Component } from 'react';
                    import { AppRegistry, View } from 'react-native';
                    
                    class FlexDimensionBasics extends Component {
                     render() {
                      return(
                       //try removing the flex:1 on the parent view
                       //the parent will not have dimensions, so the children can't expand
                       //what if you add 'height:300' instead of flex:1
                       <View style={{flex:1}}>
                        <View style={{flex: 1, backgroundColor: 'powderblue'}} />
                        <View style={{flex: 2, backgroundColor: 'skyblue'}} />
                        <View style={{flex: 3, backgroundColor: 'steelblue'}} />
                      </View>
                         );
                        }
                      };
                      
                     AppRegistry.registerComponent('AwesomeProject', ()=>FlexDimensionsBasics);
                        
