## React Native Search Box
- A simple search box with animation, inspired from ios search bar. 
- No library dependencies, lightweight, fast, flexible, customizable. 
- Support both iOS/Android devices

## Donate

[I'm feeling satisfied](http://unghotoi.com/anhtuank7c)

## Install
```
npm install --save react-native-search-box

or

yarn add react-native-search-box
```

## Demo

| Platform | Android | iOS |
|:--------:|:-------:|:---:|
| Demo gif link | ![Android](https://media.giphy.com/media/3o7bu4qW4xq15geiv6/source.gif) | ![iOS](https://media.giphy.com/media/26gR16ivWIyDlVP8s/source.gif) |

## Example code

[Example](https://github.com/crabstudio/react-native-atoz-listview/blob/master/example/src/screens/Contacts/Home.js#L162)

## Usage

```javascript
import React, { Component } from 'react';
import { TouchableHightLight, Text, View } from 'react-native';
import AtoZListView from 'react-native-atoz-listview';
import Search from 'react-native-search-box';

const rowHeight = 40;

class MyScene extends Component {

  state = {
    data: {
      "A": [
        {
          "name": "Anh Tuan Nguyen",
          "age": 28
        },
        {
          "name": "An Nhien",
          "age": 20
        },
      ],
      "Z": [
        {
          "name": "Zue Dang",
          "age": 22
        },
        {
          "name": "Zoom Jane",
          "age": 30
        },
      ]
    }
  }

    renderRow = (item, sectionId, index) => {
      return (
        <TouchableHightLight 
          style={{ 
            height: rowHeight, 
            justifyContent: 'center', 
            alignItems: 'center'}}
        >
          <Text>{item.name}</Text>
        </TouchableHightLight>
      );
    }

    // Important: You must return a Promise
    beforeFocus = () => {
        return new Promise((resolve, reject) => {
            console.log('beforeFocus');
            resolve();
        });
    }

    // Important: You must return a Promise
    onFocus = (text) => {
        return new Promise((resolve, reject) => {
            console.log('beforeFocus', text);
            resolve();
        });
    }

    // Important: You must return a Promise
    afterFocus = () => {
        return new Promise((resolve, reject) => {
            console.log('afterFocus');
            resolve();
        });
    }
    
  render() {
    // inside your render function
    return (
      <View style={{ flex: 1}}>
        <Search
          ref="search_box"
          /**
          * There many props that can customizable
          * Please scroll down to Props section
          */
        />

        <AtoZListView
          data={this.state.data}
          renderRow={this.renderRow}
          rowHeight={rowHeight}
          sectionHeaderHeight={40}
        />
      </View>
    );
  }
}
```

## Props

```
    /**
     * onFocus
     * return a Promise
     * beforeFocus, onFocus, afterFocus
     */
    beforeFocus: PropTypes.func,
    onFocus: PropTypes.func,
    afterFocus: PropTypes.func,

    /**
     * onSearch
     * return a Promise
     */
    beforeSearch: PropTypes.func,
    onSearch: PropTypes.func,
    afterSearch: PropTypes.func,

    /**
     * onChangeText
     * return a Promise
     */
    onChangeText: PropTypes.func,

    /**
     * onCancel
     * return a Promise
     */
    beforeCancel: PropTypes.func,
    onCancel: PropTypes.func,
    afterCancel: PropTypes.func,

    /**
     * async await
     * return a Promise
     * beforeDelete, onDelete, afterDelete
     */
    beforeDelete: PropTypes.func,
    onDelete: PropTypes.func,
    afterDelete: PropTypes.func,

    /**
     * styles
     */
    backgroundColor: PropTypes.string,
    placeholderTextColor: PropTypes.string,
    titleCancelColor: PropTypes.string,
    tintColorSearch: PropTypes.string,
    tintColorDelete: PropTypes.string,

    /**
     * text input
     */
    placeholder: PropTypes.string,
    cancelTitle: PropTypes.string,
    returnKeyType: PropTypes.string,
    keyboardType: PropTypes.string,
```

## LICENSE

The MIT License

Copyright (c) 2017 Crabstudio. https://github.com/crabstudio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
