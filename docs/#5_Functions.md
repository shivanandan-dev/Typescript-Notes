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

**Default Parameter**

```ts
const loginUser = (userName: string, emailId: string, password: string, isLoggedIn: boolean = false) => {
    console.log(userName, password, emailId, isLoggedIn)
}

loginUser("Shivanandan", "shiva@123", "s@s.com")
/*
* The above statement will raise an error if isLoggedIn is not given a default value in the parameter.
*/
```

### **Return Type Annotations**
- Can also add return type annotations.
- Appears after the parameter list.
- When return type annotation is used:
    - auto infers data type to the variable when called with it `(Type Inference)`.

    ```ts
    function helloWorld (): string {
        return "Hello, World!"
    }

    let greet = helloWorld()
    /*
    * Auto infers greet variable to string data type.
    */
    ```
    - does not allow the function to return value with another data type `(Type Casting)`.
    
    ```ts
    function isValid (): boolean {
        return "Hello, World!"
        /*
        * Error: Type 'string' is not assignable to type 'boolean'.
        */
    }
    ```

    - arises an error when there is conflict in function's return type and variable type.

    ```ts
    function isPrimeNumber(num: number): boolean {
        for(let i = 2; i * i <= num; i++) {
            if (number % i !== 0) return false 
        }
        return true
    }

    const randomVar: string = isPrimeNumber(20)
    /*
    * The above statement will arise an error.
    * Error: Type 'boolean' is not assignable to type 'string'.
    */
    ```

#### **Functions which returns Promises**

- to annotate the return type which returns a promise, use the `Promise` type.

```ts
async function getFavouriteNumber(): Promise<number> {
    return 5
}
```

### Anonymous Function
- The parameter type for the anonymous function is automatically inferred.

```ts
const names = ["Earth", "Venus", "Pluto"]

names.forEach((planet: string) => {
    console.log(planet)
})

/*
* In the above anonymous function, the string data type declaration is not necessary. 
* It will be automatically inferred from the array<string>
*/
```


- A good practice to mention the return type in the anonymous function.

```ts
const names = ["Earth", "Venus", "Pluto"]

names.forEach((index, planet): string => {
    return `Planet ${index}: ${planet}`
})
```