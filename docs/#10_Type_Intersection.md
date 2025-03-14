## Type Intersection `&`

- Allows you to combine multiple types into one
- Ensuring that the resulting type has all the properties form the intersected types.
- If there are conflicting properties with different types, TS will report an error in the IDE.

**Example**

```ts
type User = {
    id: number
    name: string
}

type Admin = {
    role: string
    permissions: string[]
}

type AdminUser = User & Admin // Merging both types using type intersection

const admin: AdminUser = {
    id: 1,
    name: "Shivanandan D N",
    role: "admin",
    permissions: ["create", "delete", "update"]
}

console.log(admin)
```

[Previous: Optional](/docs/%239_Optional.md) | [Next: Arrays](/docs/%2311_Arrays.md) | [Index Page](/README.md)