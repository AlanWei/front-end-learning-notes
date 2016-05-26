# `Redux`
 
1. Motivation
  1. At some point, you no longer understand what happens in your app as you have lost control over the when, why and how of its state.
  2. Libraries like `React` attempt to solve this problem (mutation and asynchronicity) in the view layer by removing both asynchrony and direct DOM manipulation. However, managing the state of your data is left up to you. This is where `Redux` enters.
  3. `Redux` attempts to make state mutations predictable by imposing certain restrictions on how and when updates can happen.

2. Three Principles
  1. Single source of truth: The state of your whole application is stored in an object tree within a single store.
  2. State is read-only: The only way to mutate the state is to emit an action, an object describing what happened.
  3. Changes are made with pure functions: To specify how the state tree is transformed by actions, you write pure reducers.

3. Actions
  1. Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using `store.dispatch()`.

4. Reducers
  1. Reducers specify how the application's state changes in response.
  2. Reducer is a pure function that takes the previous state and an action, and returns the next state.


