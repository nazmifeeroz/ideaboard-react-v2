# Ideaboard-React - V2 

#### Important: Run `brew update && brew upgrade` before continuing

Start from the root folder outside the Rails directory:
```shell
create-react-app ideaboard-react
```

Run the React app:
```shell
cd ideaboard
npm start
```

Let's add a new component called IdeasContainer.js in `src/components`
```shell
mkdir src/components
cd src/components
echo 'IdeasContainer' >> IdeasContainer.js
sublime IdeasContainer.js
```

Add this code into `IdeasContainer.js`
```javascript
import React, {Component} from 'react'

class IdeasContainer extends Component {
  render() {
    return (
      <div>
        Ideas
      </div>
    )
  }
}

export default IdeasContainer
```

Then edit `src/App.js`
```javascript
import React, { Component } from 'react';
import './App.css';
import IdeasContainer from './components/IdeasContainer'

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <h1>Idea Board</h1>
        </header>
        <IdeasContainer />
      </div>
    );
  }
}

export default App;
```

Create a new component called `IdeasContainer.js` file in src `src/components` 

```javascript
import React, {Component} from 'react'

class IdeasContainer extends Component {
  render() {
    return (
      <div>
        Ideas
      </div>
    )
  }
}

export default IdeasContainer
```

Now lets change the styles in App.css .. Remove all the styles and add the following:
```css
.App-header {
  text-align: center;
  height: 150px;
  padding: 20px;
}

.App-Intro {
  font-size: large;
}
```

In `App.js`, lets initialize the state with a construstor with ideas as an empty array:
```javascript
constructor(props) {
  super(props)
  this.state = {
    ideas: []
  }
}
```

Then lets update the state using `componentDidMount()` 

We will need to install the `axios` library to make API calls to the Rails server.

First we install axios with npm:
#### Important: Run `brew update && brew upgrade` before continuing
```shell
npm install axios --save
```

Once installed, lets import it into `IdeasContainer.js`
```javascript
import axio from 'axios'
```

Now we will use axios in `componentDidMount()`:
```javascript
componentDidMount() {
  axios.get('http://localhost:3001/api/v1/ideas.json')

    .then(response => {
      console.log(response)
      this.setState({ideas: response.data})
    })
    .catch(error => console.log(error))
}
```


