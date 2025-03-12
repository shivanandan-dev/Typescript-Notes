## **Object Types**

### Object types in parameters

```ts
function userInfo({username: string, password: string, isActive: boolean}) {
    console.log(userName, password, isActive)
}

userInfo({username: "Shivanandan D N", password: "Shiva@123", isActive: false})
```

- Annotated the type with a type with three properties.
- The type part of each property is also optional.
- Not specified, it will be assumed to be `any`.

### Object types while returning

```ts
function returnUserObj(): {username: string, isLoggledIn: boolean} {
    return {username: "Shivanandan D N", isLoggedIn: false}
}
```

- Can specify the type of an object that a function returns.
- Specified after the function's parameter list.
- Ensures that the returned object adheres to the specified type.