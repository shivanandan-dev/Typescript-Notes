## **Functions**
- Primary means of passing data around in JS.
- TS allows to specify the types of both input and output of function.

### **Parameter Type Annotations**
- When declaring a function, can add type annotation after each parameter.

**Example: When not using parameter type annotation**

```ts
function greet(name) {
    console.log(`Hello ${name}!`)
    name.toUpperCase()
}

console.log(greet('Shiva'))
console.log(greet(24))
```

- The above code will not raise any run time errors in the IDE.
- Still, this is not the right way to code.
- When used `greet(24)`, the parameter is of the type `{number}`
    - but `name.toUpperCase()` will not raise any error.
    - to avoid this parameter type annotation is used.

**Example: Right way**

```ts
function greet(name: string) {
    console.log(`Hello ${name}!`)
    name.toUpperCase()
}

console.log(greet('Shiva'))
console.log(greet(24)) // This arises the error in the IDE as the function parameter expects a string value.
```

**Error:**
```
Argument of type 'number' is not assignable to parameter of type 'string'.
```

- This way type casting is checked properly, to avoid bugs.