# Ideaboard-React - V2 

####Important: Run `brew update && brew upgrade` before continuing

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