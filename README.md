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
