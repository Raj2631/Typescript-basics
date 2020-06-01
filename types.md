# Data types in typescript.

## Introduction

TypeScript knows the JavaScript language and will generate types for you in many cases. For example in creating a variable and assigning it to a particular value, TypeScript will use the value as its type.

```ts
let myName = 'Raj';
```

The code above will create a variable myName and stores a string _Raj_ in that variable.
If you try to assign a number into myName, that'll give you error because you cannot store any other variable inside it, the type of the value you store initially while declaring the variable cannot be changed.

## Declaring variables with required type.

Since typescript is a strongly typed language, you can tell the typescript compiler the data type of the value that you want to be stored inside a particular variable.

### Primitive data types.

To declare primitive data types you just have to add ": dataType" after the variable name.

```ts
const userName: string = 'Raj';
const isThisFun: boolean = true;
const age: number = 18;
```

Again, since typescript is strongly typed, you are not allowed to mutate the value of a variable to a different type. For example:

```ts
let age: number = 18;
age = '18'; // This is wrong and will give you an error.
```

Now the question arises that what if you want your variable to be able to store multiple type of values, how will you do that?
Simple! Typescript has got you covered!
You need to use | whenever you want a variable that can store multiple data types while declaring the types.

```ts
let age: number | string;
age = 18; // Right.
age = '18'; // Right.
age = true; // WRONG.
```

You can also chain the types you want by using | between type names as follows:

```ts
let mixed: number | string | boolean;
mixed = true;
mixed = 'You can do this!';
mixed = 100;
```

### Arrays

To declare array you just need to add ": dataType[]" after the variable name.

```ts
const hobbies: string[] = ['Playing guitar', 'Coding']; // String array.
const petAge: number[] = [2, 1]; // Number array.
```

Please note that you cannot mutate the value of the array that is declared by any particular type to a different type and that applies for all elements. For example:

```ts
const hobbies: string[] = ['Playing guitar', 'Coding'];
hobbies.push('Working out'); // Right
hobbies.push(18); // WRONG.
```

You cannot mutate the data type of elements in the array, hence pushing _18_ which is a number, will give you an error.

Again, you can use | operator to store multiple types in an array, but you need to put the types inside brackets.

```ts
const mixedArray: (string | number | boolean)[] = [20, 'Guitar', false];
```

### Objects

There isn't much difference between javascript objects and typescript arrays except for the strict typing.

```ts
const person = {
  name: 'Raj',
  age: 18,
  hobbies: ['Playing guitar', 'Coding'],
};
```

You can declare an object with the properties of required type like this:

```ts
let person: {
  name: string;
  age: number;
  hobbies: string[];
};

person = {
  name: 'Raj',
  age: 18,
  hobbies: ['Playing guitar', 'Coding'],
};
```

You cannot add more properties to the objects in typescript.

```ts
let person = {
  name: 'Raj',
  age: 18,
  hobbies: ['Playing guitar', 'Coding'],
};

person.isAbove18 = true; // WRONG, cannot add new properties.
```

## Dynamic type.

Okay, enough of the strict typing, what if you don't know the type of variable that you might store on your variable?
Simple! Typescript got you covered again!
": any" is the data type that lets you store any kind of values in your variable.

```ts
let age: any = 18;
age = '18';
let array: any = [18, 20, '18', true, ['Raj']];
```

## Wrap up!

Great job following so far, the types explained above are some of the types that you will normally use.
For more detailed information on all that good stuff, you can visit the [official typescript docs!](https://www.typescriptlang.org/docs/handbook/basic-types.html)
