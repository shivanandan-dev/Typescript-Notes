## **Any Data Type**
- Datatype in TS.
- Expect any variable.
- Used when we don't know the exact type of the variable.
- Opts-out of type checking during compilation.


### **Implicit Type Casting: Any**
- Occurs when TS cannot infer the type.

**Example:**
```ts
let someValue;
/*
* In the above statement there is no value assigned or variable type is declared.
* Automatically, it will be infered as {any} type.
*/

someValue = 'Hello, world!'
someValue = 26
someValue = true
/*
* The above statements will not raise any errors in the IDE.
* As it is {any} type by implicit type casting.
*/

```

- In the above examples, 
    - the variable is not assigned a value directly
    - not assigned any data type. 
    - So the IDE cannot infer the type.
- Therefore, `{any}` type is inferred to the variables.
- This case is considered to be a bad practice.
    - As it defeats the purpose of using TS.
    - Often leads to bugs.
- Here, we declare it with a type instead of relying on type inference.


**Right way:**

```ts
let someValue: string

someValue = 'Hello, world!'
someValue = 99 // This will be raised as an error as the value assigned is in type {number} and the variable is in the type {string}.
```

### `noImplicitAny` - To escape above cases
- Falling back to `any` is just the plain JS experience.
- Using `any` often defeats the purpose of using TS.
- Run into fewer bugs, when the program is more typed.
- Turning `noImplicitAny` flag will issue an error on variables whose type is implicitly inferred as `any`