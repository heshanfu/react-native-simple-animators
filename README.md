# react-native-simple-animators

A collection of simple, reusable react-native animator wrapper components.

Currently supported styles: height, opacity, rotate, scale, translateX, translateY and width.

## Installation

```shell
npm install --save react-native-simple-animators
```

## Importing

```js
import { AnimateTranslateX } from 'react-native-simple-animators'; // ES6
var PropTypes = require('prop-types'); // ES5 with npm // TODO: Test this
```

## Usage

These animators are intended to animate their children in what I feel is a very simple way. 
Opacity and transform styles will use the nativeDriver which greatly improves performance.
Here is an example of using AnimateTranslateX to animate and wrap a simple Text component:

```js
import React from 'react';
import { Text, Easing } from 'react-native';
import { AnimateTranslateX } from 'react-native-simple-animators';

class BannerText extends React.Component {
    render() {
        return (
            <AnimateTranslateX
                initialValue={-200} // value to animate from
                finalValue={0} // value to animate to
                shouldAnimateIn // flag to start the animation
                shouldAnimateOut={false} // flag to reverse the animation (only if shouldAnimateIn was previously set)
                shouldRepeat // repeat the animation, ie. -200 => 0 and back to -200 etc.
                shouldLoop // loop the animation (must set shouldRepeat to work), ie. -200 => 0 => reset to 0 => -200 => 0 etc.
                duration={2000} // duration of the animation
                easing={Easing.ease} // easing
                style={{backgroundColor: 'red'}} // style(s) of the wrapper (array or object)
                >
                <Text>How easy was this?</Text>
            </AnimateTranslateX>
        )
    }
}

```