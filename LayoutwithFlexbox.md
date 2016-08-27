A component can specify the layout of its children using the flexbox algorithm. Flexbos is designed to provide a consistent
algorithm of different screen sizes. 

You will normally eat a combination of flexDirection, alignItems, and justifyContent to acheive the right layout. 

Flexbox works the same way on React Native as it does in CSS on the web, with few exceptions. The defaults are different,
with flexDirection defaulting to column instead of row, and alignItems defaulting to stretch instead of flex-start, and
the flex parameter supports a single number.

#Flex Direction
Adding flexComponent to a component's style determines the primary component of its layout. Should the children be organized
horizontally (row) or vertically (column)? The default is column.

                    import React, { Component } from 'react';
                    import { AppRegistry, View } from 'react-native;
                    
                    class FlexDirectionBasics extends Component {
                     render() {
                      return(
                       //Try setting flexDirection to column
                       <View style={{flex: 1, flexDirection: 'row'}}>
                        <View style={{width: 50, height: 50, backgroundColor: 'powderblue' }} />
                        <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
                        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
                       </View>
                          );
                        }
                      );
                      
                      AppRegistry.registerComponent('AwesomeProject', () => FlexDirections);
                      
#Justify Content
Adding justifyContent to a component's style determines the distribution of children along the primary axis. Should 
children be distributed at start, the center, end, or spaced evenly? Available options are flex-start, center, flex-end,
space-around, and space-between.

        import React, { Component } from 'react';
        import { AppRegistry, View } from 'react-native';
        
        class JustifyContentBasics extends Component {
         render() {
          return (
           //try setting justifyContents to 'center'
           //try setting 'flexDirection' to 'row'
           <View style = {{
            flex: 1,
            flexDirection: 'column',
            justifyContent: 'space-between',
            }}>
             <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
             <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
             <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
            </View>
            );
          }
         };
         
         AppRegistry.registerComponent('AwesomeProject', () => JustifyContentBasics);
         
#Align Basics
Adding alginItems to a component's style determines the alginment of children along the secondary axis (if the primary axis is
row, then the second is column, and vice versa). Should children be aligned at the start, the center, the end, or stretched
to fill? Avaiable are flex-start, center, flex-end, and stretch. 

For stretch to have an effect, children must not have a fixed dimension along the secondary axis. In the following example,
setting alignItems: stretch does nothing until the width: 50 is removed from children.

                  import React, { Component } from 'react';
                  import { AppRegistry, View } from 'react-native';
                  
                  class AlignItemsBasics extends Component {
                   render() {
                    return (
                     //try setting 'alginItems' to 'flex-start'
                     //try setting 'justifyContent' to 'flex-end'
                     //try setting 'flexDirection' to 'row'
                     <View style={{
                      flex: 1;
                      flexDirection: column,
                      justifyContent: 'center',
                      alignCenter: 'center',
                      }}>
                      
                      <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
                      <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
                      <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
                      </View>
                         );
                        }
                      };
                      
                     AppRegistry.registerComponent('AwesomeProject', () => AlignItemsBasic);
                     
#Going Deeper
We've covered the basics, but there are many other styles you need for layouts. 
