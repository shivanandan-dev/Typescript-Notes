## **Optional**

- Declare a property in interface or types which will be optional.
- To make a property optional, add `?` after the property name.

**Example**

```ts
type Employee {
    id: number
    name: string
    passportAvailabillity?: boolean // 'optional' used here
}

function displayEmployee (employee: Employee) {
    // 'employee.passportAvailability' is possibly 'undefined'
    if (passportAvailability)
        console.log(employee.id, employee.name, employee.passportAvailability !== undefined)
    else 
         console.log(employee.id, employee.name)
}

const newEmployee: Employee = {
    id: 123,
    name: "Shivanandan D N"
}

displayEmployee(newEmployee)
```

> **To remember**  
> In Javascript, if you access a property that doesn't exist, you will get the value `undefined` rather than runtime error. Because of this , when you read from an optional property, you will have to check for `undefined` before using it.

[Previous: Readonly](/docs/%238_Readonly.md) | [Next: Optional](/docs/%239_Optional.md) | [Index Page](/README.md)