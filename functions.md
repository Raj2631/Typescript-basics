# Functions in Typescript.

You can declare functions in typescript as the same way you did with declaring functions in javascript, i.e Either named functions or anonymous function.

Just a quick recap of functions in JS:

```ts
// Named function
function add(x, y) {
  return x + y;
}

// Anonymous function
let myAdd = function (x, y) {
  return x + y;
};
```

You can also use arrow functions.

## Adding typing to the functions.

In addition to that, typescript provides you with a "Function" type that you can declare your variables with and then you won't be able to assign anything other than a function to that variable (Though I don't really think you're gonna use it much that way)

```ts
let add: Function;
add = (x: number, y: number) => x + y;
```

OR

```ts
const add = (x: number, y: number) => x + y;
```

If we try to call the above and we only pass 1 parameter, then the typescript compiler will throw an error because you need to pass at exact 2 parameters. (Yeah, typescript is strict lol)
Please note that you need to also specify the data type of the parameters you want to receive.
You can use the | operator here too, when specifying the type of the parameter variable.

## Optional parameter

What if you want an optional parameter, which you may or may not want to pass while calling your function? You just need to add "?: [dataType]" when defining the function parameters. Eg:

```ts
const add = (x: number, y: number, c?: number) => x + y;
```

This way you are not forced by the typescript compiler to send all of the parameters. Also, always have the optional parameter as the last parameter of the function.

Note: When you are using the default value for the optional parameter, then you don't need to use "?".

## Writing the function type.

In typescript you can expand the _Function_ type according to your needs in the following way:

```ts
let add: (x: number, y: number) => number;
add = (valueX: number, valueY: number) => valueX + valueY;
add(10, 20);
```

Here you can only assign the add variable to a function that only accepts 2 parameters that are of _number_ type and that function should only return a value of type _number_.
If the function doesn’t return a value, you would use _void_ instead of leaving it off (while declaring).

A function’s type has the same two parts: the type of the arguments and the return type. When writing out the whole function type, both parts are required.

Also the name of parameters while declaring doesn't really matter, the function will be valid as long as it satisfies the parameter types. Like in the above example, x and y are dummy, they're normally just used for better readability.

To set the return type while declaring and initializing you just need to add ": [dataType]" after the parameters. For eg:

```ts
const add = (x: number, y: number): number => x + y;
```
