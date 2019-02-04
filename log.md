# 100 Days Of Code - Log
**Link to work:** [React Cryptocurrency Repo](https://github.com/stevedang-dev/React-Cryptocurrency)

### Day 1: February 01, 2019 

**Today's Progress**: 
- Set up the GitHub repo. 
- Install React Framework on my laptop.
- Fixed some errors while installing React Framework.
- Struggled with npm. 

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- 1% coding and 99% waiting to get the dependencies installed. 

===================================================================================
### Day 2: February 02, 2019

**Today's Progress**: 
- Understood how React render components using ReactDOM and div id root.
- Use ES6 class or a const to define a component name. 
- Source Code: (App.js)

```
import React from 'react';

const App = () => {
     return <h1>React Coin</h1>
}

class App extends React.Component {
    render() {
        return <div>
                    <h1>Yo!!</h1>
                </div>
    }
}

export default App;

```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Create and render components in React seems to be straight forward. Nothing complicate yet.

===================================================================================
### Day 3: February 03, 2019

**Today's Progress**: 
- JSX let us write html code right inside the js file.
- Use className for css classes because class is a reserved word in JavaScript.
- Use a pair of () for return to put the return element to its own line.
- To render a variable inside the html, put the variable inside a pair of {}.

- Create the css style with the same name as the js file. 
1. import './Header.css';, and assign classes by className.
2. inline styling:
```
const containerStyle = {
    fontSize: '40px'
}
<div style={containerStyle} className="Header-wrapper">
    Header
</div>
```
- OR: (pass in the line directly)
```
<div style={{fontSize: '40px}} className="Header-wrapper">
    Header
</div>
```

- Source code: (Header.js)
```
import React from 'react';
import logo from './logo.png';
import './Header.css';

const containerStyle = {
    fontSize: '40px'
}

const Header = () => {
    return (
        <div style={containerStyle} className="Header-wrapper">
            <img src={logo} alt="logo" className="Header-logo" />
        </div>
    );
}

export default Header;
```

- Source code: (Header.css)

```
.Header-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    background-color: #0f273d;
    width: 100%;
    height: 80px;
}
  
.Header-logo {
    position: absolute;
    top: 30px;
    left: 20px;
    width: 90px;
} 
```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Understood the component UI with JSX and Style React Components.
- There are things to watch out for in React: 
1. css className instead for class, 
2. component first letter should be in cap.
3. there are many ways to add styles to a component.
- Smooth sailing today even though it was only one hour.

===================================================================================
### Day 4: February 04, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts ༼ つ ◕_◕ ༽つ:** 

-
-
-
===================================================================================
### Day 5: February 05, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 6: February 06, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 7: February 07, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 8: February 08, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 9: February 09, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 10: February 10, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
### Day 11: February 11, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts**:
-
-
-
===================================================================================
