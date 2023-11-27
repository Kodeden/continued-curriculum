# Intersection Types in TypeScript

## Introduction

Intersection types, like union types, are a powerful feature in TypeScript that allows you to combine multiple types. However, unlike unions, intersections create a new type that includes all properties from the combined types. This means an object of an intersection type must satisfy all the requirements of the combined types.

## Syntax for Intersection Types

In TypeScript, the & operator is used to define intersection types. The syntax looks like this:

```typescript
interface InterfaceA { ... }
interface InterfaceB { ... }
type CombinedType = InterfaceA & InterfaceB;
```

## Applying an Intersection to the `Person` Interface

Let's extend the `Person` example from the unions lesson (you should reference the same code that you have been writing in the previous lessons):

Create a new `interface`:

```typescript
interface Employee {
  company: string;
  jobTitle: string;
  salary: number;
}
```

Now, create a new `type` that is an intersection of `Person` and `Employee`:

```typescript
type EmployeePerson = Person & Employee;
```

In this example, `EmployeePerson` is an intersection of `Person` and `Employee`. This means an `EmployeePerson` must have all the properties of `Person` **and** `Employee`.

## Examples of Intersection Types

```typescript
const employee: WorkingPerson = {
  id: 2,
  firstName: "Alice",
  lastName: "Smith",
  age: 28,
  address: {
    street: "456 Main St",
    city: "Metropolis",
    state: "NY",
    zip: 10001,
  },
  company: "Globex Corporation",
  jobTitle: "Software Developer",
};

console.log(greet(employee)); // Works as employee is a Person
```

## Comparison with Union Types

Let's compare the intersection type `EmployeePerson` with the union type `Person | Employee`:

```typescript
type Person = {
  name: string;
  age: number;
};

type Employee = {
  company: string;
  department: string;
};

// An EmployeePerson is both a Person and an Employee
type EmployeePerson = Person & Employee;

// An EmployeeOrPerson is either a Person or an Employee
type EmployeeOrPerson = Person | Employee;
```

Naturally, `EmployeeOrPerson` doesn't make much sense.

## Additional 🎶

As with the **union** type,the syntax has some similarity with JS.

With the **union** type, it was an an 'OR' with `|` instead of `||`. Similarly, with _intersection_ types, it's a type of 'AND', but just `&` instead of `&&`.

## Challenge: 🧑‍🎓

We'll keep the challenge a bit less challenging. For this challenge, you'll need to create a new interface called `Student` that has the following properties:

- `university` - string
- `major` - string
- `graduationYear` - string

Then, create a new type called `StudentPerson` that is an intersection of `Person` and `Student`.

Finally, create a new `student` object that is of type `StudentPerson` and pass it to the `greet` function.
