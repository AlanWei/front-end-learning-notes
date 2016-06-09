# `Redux`
 
1. Motivation
  1. At some point, you no longer understand what happens in your app as you have lost control over the when, why and how of its state.
  2. Libraries like `React` attempt to solve this problem (mutation and asynchronicity) in the view layer by removing both asynchrony 
      and direct DOM manipulation. However, managing the state of your data is left up to you. This is where `Redux` enters.
  3. `Redux` attempts to make state mutations predictable by imposing certain restrictions on how and when updates can happen.

2. Three Principles
  1. Single source of truth: The state of your whole application is stored in an object tree within a single store.
  2. State is read-only: The only way to mutate the state is to emit an action, an object describing what happened.
  3. Changes are made with pure functions: To specify how the state tree is transformed by actions, you write pure reducers.

3. Actions
  1. Actions are payloads of information that send data from your application to your store. They are the only source of information for 
      the store. You send them to the store using `store.dispatch()`.
      
4. Reducers
  1. Reducers specify how the application's state changes in response.
  2. Reducer is a pure function that takes the previous state and an action, and returns the next state.
  
5. Store
  1. Holds application state.
  2. Allows access to state via `getState()`.
  3. Allows state to be updated via `dispatch(action)`.
  4. Registers listeners via `subscribe(listener)`.
  5. Handlers unregistering of listeners via the function returned by `subscribe(listener)`.
  
6. Data Flow
  1. Redux architecture revolves around a stric unidirectional data flow.
  2. The data lifecycle in Redux follows these 4 steps:
  
    1. You call `store.dispatch(action)`. An `action` is a plain object describing what happened.
    ~~~
      { type: 'LIKE_ARTICLE', articleId: 42 }
    ~~~
    2. The Redux store calls the reducer function you gave it. The store will pass two arguments to the `reducer`: the current state tree 
        and the action.
    ~~~
      let nextState = todoApp(previousState, action)
    ~~~
    3. The root reducer may combine the output of multiple reducers into a single state tree.
    4. The Redux store saves the complete state tree returned by the root reducer.

7. Async Actions
  1. Actions
    1. An action informing the reducers that the request begin.
    2. An action informing the reducers that the request finished successfully.
    3. An action informing the reducers that the request failed.