## **Union Types**

- A types fromed form two or more types.
- Reperesenting values that may be one of those types.

**Example**

```ts
function printCharacterData(character: number | string) {
    console.log(character)
}

// OK
printCharacterData("Ichigo")
// OK
printCharacterData(27)
// Error
printCharacterData({ character: 2234 })
//                   ^ Error: Argument of type '{ character: number; }' is not assignable to parameter of type 'string | number
```

> **Note**: *The seperator of the union members is allowed before the first element*

**Example**

```ts
function printTextOrNumberOrBool(
    textOrNumberOrBool:
        | string
        | number
        | boolean
) {
    console.log(textOrNumberOrBool)
}
```

### **Working with Union Types**

- TypeScript will only allow an operation if it is valid for every member of the union. 
- For example: if you have the union `string | number`, you can’t use methods that are only available on `string`.

**Example**

```ts
function printId(id: number | string) {
    console.log(id.toUpperCase())
//              ^ Error: Property 'toUpperCase' does not exist on type 'string | number'. Property 'toUpperCase' does not exist on type 'number'. 
}
```

- The solution for this is to *narrow* the union with code

**Example**

```ts
function printId(id: number | string) {
  if (typeof id === "string") {
    // In this branch, id is of type 'string'
    console.log(id.toUpperCase());
  } else {
    // Here, id is of type 'number'
    console.log(id);
  }
}
```

**Example**

```ts
function welcomePeople(x: string[] | string) {
  if (Array.isArray(x)) {
    // Here: 'x' is 'string[]'
    console.log("Hello, " + x.join(" and "));
  } else {
    // Here: 'x' is 'string'
    console.log("Welcome lone traveler " + x);
  }
}
```

- If every member in a union has a property in common, you can use that property without narrowing.
- For Example: Both `string` and `number` got slice method.

**Example**

```ts
// Return type is inferred as number[] | string
function getFirstThree(x: number[] | string) {
  return x.slice(0, 3);
}
```

[Previous: Arrays](/docs/%2311_Arrays.md) | [Next: ]() | [Index Page](/README.md)