install redux in cli:
```PowerShell
	npm i redux redux-toolkit
```

![[assets/redux.gif]]


`index.js`
```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import {createStore} from 'redux'
import {Provider} from 'react-redux'

const defaultState = {
  cash: 234,
}


const reducer = (state = defaultState, action) => {
  switch (action.type){ 
  case "ADD_CASH":
    return {...state, cash: state.cash + action.payload}

  case "GET_CASH":
    return {...state, cash: state.cash - action.payload}



  default:
    return state
  }
}

const store = createStore(reducer)

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <Provider store={store}>  
    <App />
    </Provider>  
  )

```

`App.js`
```js
import {useDispatch, useSelector} from 'react-redux'


function App() {

  const dispatch = useDispatch()
  const cash = useSelector(state => state.cash)
  console.log(cash)

  return (
    <div className="App">
        
    </div>
  );
}

export default App;

```

that will return `cash` in console

#react #redux #js