# ComponentBasedUINotes

## Notes from Class Lecture 26 10/24/22

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Review notes

- What is state?

  information about the compent which can change

How do you set state?

- ```Javascript
  constructor(props){
    super(props);
    this.state = {
      key: value
    }
  } ```

- What are props?
  - also a POJO, key difference is they are passed to the component (like function parameters) where as state is managed within the component. A component CANNOT change its props. Passed in, not out.

- Can props change?
  - if that prop is state of another prop, remember state can be manipulated.

- Can component state change?
  - Yes indeed.

- What React lifecycle method must every CLASS component have?
  - render() with a return

- What React lifecycle method must be used when establishing class component state?
  - constructor

- What React lifecycle method would you use to load data on a page without user interaction?
  - componentDidMount()

- In what order are React lifecycle methods called within a class?
  - constructor, render, componentDidMount

## React Testing

### Behavior Driven Deployment

- React Testing Library
  - sits on the top of jest
  - significant React specific functionality

- How will my component behave as user interacts with the app / component?
- what do we expect to test for? behavior? functionality (in our reducers / pure functions) both.. it depends.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Notes from Class 27

## Review Notes

> What is a hook? A special function that lets you "hook into" React features. For example, useState is a hook that lets you add React state to function components.

```JavaScript
let Keelen {
  name: 'Keelen',
  age: 24
  }

  let chico = {
    name: 'Chico Rancho',
    age: 5
    }

let family = [Keelen, chico]

const [first] = family

console.log(first);

// How to set up State in a functional component
// Remember, You can not change state!
const [count, setCount] = useState(0);
const [moreState, setMoreState] = useState(family);

// how do I access "Chico Ranch" from the moreState variable
moreState[1].name

// increment count
let newCount = count + 1;
setCount(newCount);

```

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Notes from Class 28

## Review Note

- In function components, we have ONE lifecycle hook that can handle "everything": useEffect();

### useEffect() Hook

WHY

- Manage lifecycle events
- Manage Side-effects

useEffect will handle all of the following cases:

- Must do the thing correctly.....
  - every time an event occurs (greedy)
  - can do a thing ONCE when an event occurs
  - when state is updated
  - when a component unmounts - important to turn things off!

### NOTE

- We are using a dev environment build. We may see things happen more then "ONCE"
- msw for testing can be an option for integration testing. not sure if it's necessary.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Notes from Class 29

## Review - Notes

## Reduce Pattern

``` javascript
let arr = ['ryan, lucky'];

let objArr = arr.reduce((newArr, objName) => {
  // newArr = [...newArr, {name: objName}];
  newArr.push({name: objName});
  return newArr;
}, []);

console.log(objArr);
```

- What is returned? a new object, aka an array of objects

### Pure Function

> a function that takes in input, does some processing and returns a new object

### useReducer() Hook

- can in use in place of useState();
- can manipulate state in more complex ways than useState();

``` javascript
let initialState = {
  name: 'Seasame Street',
  characters: [],
}


function reducer(state, payload){
  return {...state, characters: [...state.characters, payload]};
}


let updatedState = reduce(initialState, 'Elmo');
```

React realizes that managing individual state variables is complex across many components

- When updating "state", each component just needs to know what to give the reducer.

