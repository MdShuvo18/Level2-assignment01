
## 🧾 Interfaces vs Types in TypeScript: What’s the Difference?

If you are learning TypeScript, you’ve probably seen both `interface` and `type`. They look very similar and can often be used to do the same thing. But they have some differences.

In this blog, we will talk about what makes them different, and when you should use one over the other — using simple language.

---

### ✅ What Are They?

Both `interface` and `type` are used to describe the shape of data. That means they help tell TypeScript what kind of values an object should have.

Example using an **interface**:

```ts
interface User {
  name: string;
  age: number;
}
```

Example using a **type**:

```ts
type User = {
  name: string;
  age: number;
}
```

---

### ✨ What is Declaration Merging?

This is a special feature of `interface`. It means you can define the same interface in two places, and TypeScript will combine them.

```ts
interface Car {
  brand: string;
}

interface Car {
  model: string;
}

// Now Car has both brand and model
```

You **can’t** do this with `type`.

---

### 🧠 When Should You Use Interface?

Use `interface` when:

* You are describing the shape of an object.
* You are working with class-based code.
* You want to extend or merge shapes easily.

Use `type` when:

* You need union or intersection types.
* You are working with tuples, functions, or advanced types.
* You want more flexibility.

Just remember:
> Interfaces are best for structure, and types are best for flexibility.





In TypeScript, the `keyof` keyword is used to obtain the keys of a given type or object. It essentially extracts the union of all the property names (keys) of the type or object. This is especially useful for creating types that work with specific object keys dynamically, enhancing type safety.

### Example:

```typescript
interface Person {
  name: string;
  age: number;
  address: string;
}

type PersonKeys = keyof Person; 

let key: PersonKeys;
key = "name";    
key = "age";     
key = "address"; 
key = "email";   
```

### Explanation:

* `keyof Person` creates a type that represents the union of the string literal types `"name" | "age" | "address"`.
* The `key` variable can only accept one of these keys (`"name"`, `"age"`, or `"address"`), ensuring type safety when accessing properties of the `Person` object.

This can also be useful in functions or scenarios where you want to enforce the use of valid keys in a dynamic manner, rather than hardcoding strings.
