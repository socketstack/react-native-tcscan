# react-native-tcscan

React-Native 二维码扫描插件，同时支持 iOS & Android
     
##	Requirements

* Requires iOS 7 or later

##	Installation
*	`1. npm install -g rnpm`
* 	`2. npm install react-native-tcscan`
* 	`3.	rnpm link react-native-tcscan`

#### Note:
*	rnpm requires node version 4.1 or higher

# Usage

    import React, { Component } from 'react';
    import {
      AppRegistry,
      StyleSheet,
      Text,
      View,
      TouchableOpacity,
      NativeModules
    } from 'react-native';

    const rnModule = NativeModules.tcscan;

    class Demo extends Component {

     _onPressButton(){
    	     //event: scan result
          rnModule.scan((event)=>{alert(event);});
     }

      render() {
        return (
          <View style={styles.container}>
               <TouchableOpacity onPress={this._onPressButton}>
                <Text> scan</Text>
              </TouchableOpacity>
          </View>
        );
      }
    }
    const styles = StyleSheet.create({
        container: {
            flex: 1,
            justifyContent: 'center',
            alignItems: 'center',
            backgroundColor: '#F5FCFF',
        },
    });
    AppRegistry.registerComponent('Demo', () => Demo);
