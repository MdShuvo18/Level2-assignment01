
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

