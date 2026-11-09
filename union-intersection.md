# Combining Union and Intersection in TypeScript

## Introduction
TypeScript helps to define types of the data in our applications. Union and Intersection are two useful especial type in TypeScript. Union allows a variable to accept values from multiple possible types. and Intersection combine multiple types into one type.


## Example
we will represent this using student and teacher data.

```typescript
type Student = {
    name: string;
}
type Teacher = {
    subject: string;
}
type Age = {
    age: number;
}

type SchoolMember = Student | Teacher

type SchoolMemberData =  SchoolMember & Age;

const members:SchoolMemberData = {
    name: "Nantu",
    age:25,
}

```

## How it works:
Student | Teacher -> A school member can be a Student OR Teacher. <br>
SchoolMember & Age -> Adds the Age requirements to either type. <br>
members -> the member object is Valid because it contains the name property from Student and the age property from age.




## Conclusion
Union provides different type option, while intersection adds common requirement. combining both help us create flexible and reusable types. this approach is useful when work with multiple object and some requierd properties. 