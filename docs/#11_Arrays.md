## **Arrays**

- By default when an empty array is declared, it will be assigned to `never[]`.

```ts
const animeCharacters = []
//    ^ const animeCharacters: never[]

animeCharacters.push("Ichigo")
//                   ^ Error: Argument of type '"Ichigo"' is not assignable to parameter of type 'never'.
```

```ts
const animeCharacters: [] = []
//    ^ const animeCharacters: []

animeCharacters.push("Ichigo")
//                   ^ Error: Argument of type '"Ichigo"' is not assignable to parameter of type 'never'.
```

- To avoid this always assign the type to array with the respective datatype.

**Example**

```ts
const animeCharacters: string[] = [] // Right way
//    ^ const animeCharacters: string[]

animeCharacters.push("Ichigo")
```

**Another way**
```ts
const animeCharacters: Array<string> = []

animeCharacters.push("Ichigo")
```

### Array of Types

- Can define an array of objects using a custom type.
- This  allows to enforce the shape of each object within the array, ensuring the type safety.

**Example**

```ts
type AnimeCharacter = {
    name: string,
    gender: string,
    animeName: string,
    power: number
}

const animeCharacters: Array<AnimeCharacter> = []

animeCharacters.push({
    name: "Ichigo",
    gender: "male",
    animeName: "bleach",
    power: 97
})
```

[Previous: Type Intersection](/docs/%2310_Type_Intersection) | [Next: ]() | [Index Page](/README.md)