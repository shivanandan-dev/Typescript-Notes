## **Type Aliases**

- Defining types with a custom name.
- Can be used for primitives like `string` or more complex types such as `objects` and `arrays`.

**Example**
```ts
type alphanum = string | number

let username: alphanum = "shiva123"
username += 4
```

**Exmaple**
```ts
type User = {
    name: string;
    email: string;
    isActive: boolean;
}

function createUser(user: User){}

createUser({name: "Shivanandan", email: "", isActive: false})
```

[Previous: Object Types](/docs/%236_Object_types.md) | [Next: ReadOnly](/docs/%238_Readonly.md) | [Index Page](/README.md)