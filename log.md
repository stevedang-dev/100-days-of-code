# 100 Days Of Code - Log
1. **Link to work:** [React Cryptocurrency Repo](https://github.com/stevedang-dev/React-Cryptocurrency)
2. **Link to Crypto Currency API:** [Cryptocurrency API](https://api.udilia.com/coins/v1/cryptocurrencies), [API Docs](https://udilia.com/docs/cryptocurrencies/v1)
3. **Quick Look:**

![ss1](https://user-images.githubusercontent.com/32247767/52514147-6abc4180-2bdd-11e9-9380-ee63b4554e28.png)


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
- JSX let us write HTML code right inside the js file.
- Use className for CSS classes because the class is a reserved word in JavaScript.
- Use a pair of () for the return to put the return element to its own line.
- To render a variable inside the HTML, put the variable inside a pair of {}.

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
1. CSS className instead for class,
2. component first letter should be in capitalized.
3. there are many ways to add styles to a component.
- Smooth sailing today even though it was only one hour.

===================================================================================
### Day 4: February 04, 2019

**Today's Progress**: 
- Understood when to use functional component, when to use class component. 
```
Simply because for presentation(use functional component), for state or life cycle hooks(use class component).
```
- Understood React State: 
```
An object that that determines how our component renders and behaves.
Create dynamic interactive components.
```
- Constructor super(): 
```
For a subclass because all of the created classes are subclasses of React.Component Class.
```
- React Life Cycle Hooks: componentDidMount, componentWillMount, ...
- Call the [Crypto Currency API](https://udilia.com/docs/cryptocurrencies/v1), and work with the response data. 
- To assign data to the state, use this.setState({}). For example:

```
this.setState({ loading: true });
this.setState({ currencies: data.currencies, loading: false });
this.setState({ error: error.errorMessage, loading: false });
```
- Every time the data changed, state object updates the data - Re-renders.
- Understood how the component make a get request call.
- Source code:
```
import React from 'react';

class List extends React.Component {
    constructor() {
        super();
        this.state = {
            loading: false,
            currencies: [],
            error: null
        }
    }

    componentDidMount() {
        this.setState({ loading: true });

        fetch('https://api.udilia.com/coins/v1/cryptocurrencies?page=1&perPage=20')
            .then(response => {
                return response.json().then(json => {
                    return response.ok ? json : Promise.reject(json);
                });
            })
            .then((data) => {
                console.log('Success', data);

                this.setState({ 
                    currencies: data.currencies,
                    loading: false
                });
            })
            .catch((error) => {
                console.log('Error', error);
                this.setState({
                    error: error.errorMessage,
                    loading: false
                });
            });
    }

    render() {
        console.log(this.state);
        if (this.state.loading) {
            return <div>Loading...</div>
        }
        return (
            <div>Test</div>
        );
    }
}

export default List;
```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Interesting materials on how to create the component right based on presentation purpose 
- or state and life cycle hooks purpose
- Subclass in React will need to have the super() method, call the CryptoCurrency API 
- and assign data to the state object by this.setState({ key: value, ... });
- and the fetch data function should be in componentDidMount() method.


===================================================================================
### Day 5, 6, 7, 8: February 05, 06, 07, 08, 2019
- Tests, assignments and work took a lot of time away for side prject. 
- Coming up midterns, assignments and work.

**Today's Progress**: 
- Understood the reponse, reject, resolve in Promises. 
- Created the Promise reponse handler to process reponse either sucess or not.
```
export const handleResponse = (response) => {
    return response.json().then(json => {
        return response.ok ? json : Promise.reject(json);
    });
}
```
- Array.map(item => (item.data));
```
<div>
    {this.state.currencies.map((currency) => (
        <div>
            {currency.id}
        </div>
    ))}
</div>
```
- Change the percentage and the arrow based on the percentage:
```
renderChangePercent(percent) {
    if (percent > 0) {
        return <span className="percent-raised">{percent}% &uarr;</span>
    } else if (percent < 0) {
        return <span className="percent-fallen">{percent}% &darr;</span>
    } else {
        return <span>{percent}%</span>
    }
}
```
- ES6 fun stuff:
```
// ES6:
// const loading = this.state.loading;
// const error = this.state.error;
// const currencies = this.state.currencies;

const { loading, error, currencies } = this.state;
```
- Reusable api:
```
export const API_URL = 'https://api.udilia.com/coins/v1'; 
```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Busy, busy, busy but I got back to the game. Let's do this.


===================================================================================
### Day 9: February 09, 2019

**Today's Progress**: 
- Understood how properties work in React.
- Passing data from parent component => child component:
- Parent Component:
```
renderChangePercent(percent) {
    if (percent > 0) {
        return <span className="percent-raised">{percent}% &uarr;</span>
    } else if (percent < 0) {
        return <span className="percent-fallen">{percent}% &darr;</span>
    } else {
        return <span>{percent}%</span>
    }
}

const { loading, error, currencies } = this.state;

<Table 
    currencies={currencies}
    renderChangePercent={this.renderChangePercent}    
/>
```
- Child Component:
```
const Table = (props) => {
...
<tbody className="Table-body">
    {props.currencies.map((currency) => (
        <tr key={currency.id}>
...
<td>
    {props.renderChangePercent(currency.percentChange24h)}
</td>
}
```
- Check property type by the prop-type dependency.
```
// Checking type:
Table.propTypes = {
    /* Error:
        Warning: Failed prop type: Invalid prop `currencies` of type 
        `array` supplied to `Table`, expected `string`.
    */
    // currencies: PropTypes.string,
    currencies: PropTypes.array.isRequired,
    renderChangePercent: PropTypes.func.isRequired
}
```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Stay hungry and humble. 

===================================================================================
### Day 10: February 10, 2019

**Today's Progress**: 
- More practice on sharing data through props in React.
- There are two ways to pass props' data to a function.
```
1. onClick={() => handlePaginationClick('prev')}
2. onClick={handlePaginationClick.bind(this, 'next')}
```
- Bind the method in the constructor:
```
Method 1:
    handlePaginationClick = (direction) => {
        let nextPage = this.state.page;
        nextPage = (direction === 'next') ? nextPage + 1 : nextPage - 1;
        this.setState({ page: nextPage });
    }

Method 2:
    this.handlePaginationClick = this.handlePaginationClick.bind(this);

```
- this.setState takes a call back as its second params
```
this.setState({ page: nextPage }, () => {
    this.fetchCurrencies();
});
```
- Source Code:
```
import React from 'react';
import './Pagination.css';
import PropTypes from 'prop-types';

const Pagination = (props) => {
    const { page, totalPages, handlePaginationClick } = props;
    return (
        <div className="Pagination">
            <button className="Pagination-button"
                onClick={() => handlePaginationClick('prev')}
                disabled={page <= 1}
            >
                &larr;
            </button>
            <span className="Pagination-info">
                Page <b>{page}</b> of <b>{totalPages}</b>
            </span>
            <button 
                className="Pagination-button"
                onClick={() => handlePaginationClick('next')}
                disabled={page >= totalPages}
            >
                &rarr;
            </button>
        </div>
    );
}

// page, totalPages, handlePaginationClick
Pagination.prototype = {
    page: PropTypes.number.isRequired,
    totalPages: PropTypes.number.isRequired,
    handlePaginationClick: PropTypes.func.isRequired,
}

export default Pagination;

```

**Thoughts ༼ つ ◕_◕ ༽つ:** 
- Understood more about props and shared data.
-
-
===================================================================================
### Day 8: February 08, 2019

**Today's Progress ༼ つ ◕_◕ ༽つ:** 
- 
- 
-

**Thoughts ༼ つ ◕_◕ ༽つ:** 
-
-
-
===================================================================================
### Day 9: February 09, 2019

**Today's Progress ༼ つ ◕_◕ ༽つ:** 
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

**Thoughts ༼ つ ◕_◕ ༽つ:** 
-
-
-
===================================================================================
### Day 11: February 11, 2019

**Today's Progress**: 
- 
- 
-

**Thoughts ༼ つ ◕_◕ ༽つ:** 
-
-
-
===================================================================================
