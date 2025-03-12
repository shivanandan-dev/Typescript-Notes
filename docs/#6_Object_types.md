## **Object Datatype**

### Object datatype in parameters

```ts
function userInfo({username: string, password: string, isActive: boolean}) {
    console.log(userName, password, isActive)
}

userInfo({username: "Shivanandan D N", password: "Shiva@123", isActive: false})
```

- Annotated the type with a type with three properties.
- The type part of each property is also optional.
- Not specified, it will be assumed to be `any`.

### Object datatype while returning

```ts
function returnUserObj(): {username: string, isLoggledIn: boolean} {
    return {username: "Shivanandan D N", isLoggedIn: false}
}
```

- Can specify the type of an object that a function returns.
- Specified after the function's parameter list.
- Ensures that the returned object adheres to the specified type.

## **Bad behaviour of objects**

```ts
function createUser({username: string, email: string}) {
    console.log(username, email)
} 

const user = {username: "Shivanandan D N", email: "s@s.com", isLoggedIn: true}

createUser(user)
```

- The above example shows the bad behaviour in **objects**.
- This is because the function `createUser()` parameters does not have `isLogged` as one of its parameter in the object.
- But it is passed indirectly through a user object in its function call `createUser(user)`.
- Still, this doesn't raise any error in the IDE.
- This is considered a bad behaviour in objects.

[Previous: Functions](/docs/%235_Functions.md) | [Next: Type Aliases](/docs/%237_Type_Aliases.md) | [Index Page](/README.md)