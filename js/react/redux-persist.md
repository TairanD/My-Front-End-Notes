# redux-persist

### What is redux-persist?
Redux Persist is a commonly used library that can persist Redux state to local storage, allowing it to be restored when 
the user closes and reopens the browser.

To achieve data saving when the user closes the browser and reopens it:
1. use Redux Persist to persist the Redux state
2. configure Redux Persist to save the state to localStorage or other persistent storage

### How to use it?

This way, when the
user closes the browser and reopens it, the Redux state will be loaded from storage and restored, allowing the user to 
continue from where they left off.

``` 
import { createStore } from 'redux';
import { persistStore, persistReducer } from 'redux-persist';
import storage from 'redux-persist/lib/storage'; // defaults to localStorage

import rootReducer from './reducers';

const persistConfig = {
  key: 'root',
  storage,
};

const persistedReducer = persistReducer(persistConfig, rootReducer);

const store = createStore(persistedReducer);
const persistor = persistStore(store);

export { store, persistor };

```

In this example, `persistConfig` specifies the configuration for Redux Persist, where `key` is the storage key and `storage`
specifies the storage engine, using localStorage here. Then, the root reducer and `persistConfig` are passed to 
`persistReducer` to create a persistent reducer. Finally, a **persistent** `store` is created using `persistStore`, 
and both the `store` and `persistor` are exported.

Then, replace React-Redux application's store with this one and ensure that `persistor.persist()` is called before 
rendering the application:
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';
import { PersistGate } from 'redux-persist/integration/react'; 
import { store, persistor } from './store'; 
import App from './App';

// execute persistor.persist() before rendering
persistor.persist();

ReactDOM.render(
  <Provider store={store}>
    <PersistGate loading={null} persistor={persistor}> 
      <App />
    </PersistGate>
  </Provider>,
  document.getElementById('root')
);
```
Typically, we call `persistor.persist()` in the application's entry file (e.g., index.js or App.js). 
This ensures that before rendering your application, the state in the Redux store has been persistently saved.

