## ReadOnly

- Makes a property as a read-only.
- Can be accessed outside the class.
- Their values cannot be changed.
- Since its read only, they need to be
    - initialized while declaration.
    - initialized inside the class constructor.

**Example**

```ts
type User = {
    readonly _id: string // readonly used here.
    name: string
    email: string
    isActive: boolean
}

const newUser: User = {
    _id: "1234",
    name: "Shivanandan D N",
    email: "s@s.com",
    isActive: false
}

newUser.email = "h@h.com"
newUser._id = "1234"
/*
* Above statment will raise an error.
* Error: Cannot assign to '_id' because it is a read-only property.
*/
```

[Previous: Type Aliases](/docs/%237_Type_Aliases.md) | [Next: ]() | [Index Page](/README.md)