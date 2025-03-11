## **Type Inference**
- Process that automatically assign types to variables, functions and expressions.
- Done at compile time or runtime.

Example
```ts
const  pi = 3.14 // type {number} is automatically assigned here.

pi = 'Shivanandan' // This will raise as an error in the IDE as type {number} is given to the variable pi using type inference.
```

For ref: [Type annotation on Variables](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-annotations-on-variables)