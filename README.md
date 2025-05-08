# B5-Assignment-1

1. Differences Between Interfaces and Types in TypeScript
In TypeScript, both interface and type are used to define the shape of an object or a set of values, but there are key differences between them.

Interfaces:

Primarily used for defining object shapes.

Can be extended or implemented using extends and implements.

Interfaces can only define object types and are open to declaration merging, meaning you can define an interface multiple times and TypeScript will combine them.

typescript
Copy
Edit
interface User {
  name: string;
  age: number;
}
Types:

More flexible than interfaces as they can define primitives, unions, intersections, tuples, and even complex objects.

Cannot be merged, unlike interfaces.

typescript
Copy
Edit
type User = {
  name: string;
  age: number;
};
While both are widely used to enforce structure and type safety, interfaces are usually preferred for object-oriented design, whereas types offer more flexibility and can be used in more complex scenarios like unions and intersections.



2. The keyof Keyword in TypeScript
The keyof keyword is a unique and powerful feature in TypeScript. It allows us to extract the keys of a given type and use them to create types that are limited to those keys.

Example:

typescript
Copy
Edit
interface Person {
  name: string;
  age: number;
}

type PersonKeys = keyof Person;  // "name" | "age"
In this example, PersonKeys is a union type of "name" and "age", representing the keys of the Person interface.

3. Understanding the Difference Between any, unknown, and never Types in TypeScript
In TypeScript, types like any, unknown, and never are used in different contexts to ensure proper type safety.

any:

The any type allows you to opt-out of TypeScript's type checking.

Use this when you're unsure about the type, but you still want to assign it to a variable.

typescript
Copy
Edit
let value: any = 5;
value = "Hello";
unknown:

Similar to any, but safer. You can’t perform operations on unknown without first asserting or checking its type.

typescript
Copy
Edit
let value: unknown = 5;
if (typeof value === "string") {
  console.log(value.length); // Safe operation
}
never:

The never type represents values that will never occur. It is used for functions that throw errors or have infinite loops.

typescript
Copy
Edit
function throwError(message: string): never {
  throw new Error(message);
}
4. The Use of Enums in TypeScript
Enums are a great way to define a set of named constants. TypeScript provides both numeric and string enums.

Numeric Enum:
Numeric enums start with 0 by default and increment by 1, but you can assign custom values as well.

typescript
Copy
Edit
enum Direction {
  Up,    // 0
  Down,  // 1
  Left,  // 2
  Right  // 3
}

console.log(Direction.Up); // Output: 0
String Enum:
String enums allow you to explicitly assign string values to the enum members.

typescript
Copy
Edit
enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT"
}

console.log(Direction.Up); // Output: "UP"
Enums are a useful way to define and manage sets of constants, ensuring clarity and reducing the chances of errors from using incorrect values.
 
