# Type Alias vs. Interface in TypeScript: key Differences And when should to use each one?

## Introduction
Type Alias and Interface both define type in TypeScript. Both help to prevent type related mistakes
interface focus on object while type aliases support union, tuple, and primitive. In this blog, we will explore their key differences and understand when to use each one.

```typescript
interface Course { name:string; price:number; }
type CourseInfo = { name:string; price: number;}
```

<br>

<br>

## Main differences

| Options             | Type Alias | Interface   |
| ------------------- | ---------- | ----------- |
| Primitive type      | Y          | N           |
| Union type          | Y          | N           |
| Tuple type          | Y          | N           |
| Declaration merging | N          | Y           |
| Intersection        | Y          | Uses Extends |


## Example

Type Alias - Union

```typescript
type  Role = "Admin" | "User" | "Staff"
type ID = string | number
```

A Type alias support



Interface - Extension

```typescript
interface Company {
    name:string
}

interface Employee extends Company {
    salary:number
}
```

Type Alias - Intersection

```typescript
type Company = {
    name:string
}

type Employee = Company & {
    salary:number
}
```

Both combine object types data


Interface - Declaration merging

```typescript
interface Person {
    name:string
}

interface Person {
    age:number
}
```

Both have merged in one object:

```typescript
{name:string; age:number}
```

a type alias cannot be declared multiple with the same name same scope.

<br>
<br>

## When use each one

Use Interface when:

work with object structure,Classes, or extendable object model.

Use type when:

Working with union, tuples, Primitive, intersection, And complex type transformation.

note: TypeScript's documentation suggests using interface as a default until you need a specific use to type.

<br>
<br>

## Conclusion

Both Type and Interface in TypeScript very useful feature. Use Interface defining and extending object, type alias use for tuple, union, Primitive and more complex type.
