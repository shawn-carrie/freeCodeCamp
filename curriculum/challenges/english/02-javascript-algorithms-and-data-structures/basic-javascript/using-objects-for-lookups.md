---
id: 56533eb9ac21ba0edf2244ca
title: Using Objects for Lookups
challengeType: 1
videoUrl: 'https://scrimba.com/c/cdBk8sM'
forumTopicId: 18373
dashedName: using-objects-for-lookups
---

# --description--

Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data — or data that can be organized into columns (keys) and rows (values) – then using an object and its properties to "lookup" values that correspond to the property can be more efficient than a chain of `if/else` or a multiple-case `switch` statement. 

Using objects as a dictionary to lookup values is most useful when input data is limited to a certain range — in the following example, for instance, we will look up the numeric order of letters in the English alphabet – in reverse order.

Here is an example of using an object to perform a simple reverse alphabet lookup:
Since Z is the last letter of the alphabet, we will place it at number 1 in our reversed alphabet;
Y is the second to last letter of the alphabet, we will place it at number 2, and so on.

```js
const reverseAlphabet = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};

const thirdLetter = reverseAlphabet[2];
const lastLetter = reverseAlphabet[25];

let value = 2;
const valueLookup = reverseAlphabet[value];
```

`thirdLetter` is the string `Y`, `lastLetter` is the string `C`, and `valueLookup` is the string `Y`.

# --instructions--

Instead of using a bulky `switch` statement, let's swap this code for a more lightweight object to perform our lookup operation.

Convert the switch statement into an object called `lookup` – which will store coded words from the [The International Radiotelephony Spelling Alphabet](https://en.wikipedia.org/wiki/NATO_phonetic_alphabet). 

Then, use it to look up `val` and assign the associated string to the `result` variable.

# --hints--

`phoneticLookup("alpha")` should equal the string `Adams`

```js
assert(phoneticLookup('alpha') === 'Adams');
```

`phoneticLookup("bravo")` should equal the string `Boston`

```js
assert(phoneticLookup('bravo') === 'Boston');
```

`phoneticLookup("charlie")` should equal the string `Chicago`

```js
assert(phoneticLookup('charlie') === 'Chicago');
```

`phoneticLookup("delta")` should equal the string `Denver`

```js
assert(phoneticLookup('delta') === 'Denver');
```

`phoneticLookup("echo")` should equal the string `Easy`

```js
assert(phoneticLookup('echo') === 'Easy');
```

`phoneticLookup("foxtrot")` should equal the string `Frank`

```js
assert(phoneticLookup('foxtrot') === 'Frank');
```

`phoneticLookup("")` should equal `undefined`

```js
assert(typeof phoneticLookup('') === 'undefined');
```

You should not modify the `return` statement

```js
assert(code.match(/return\sresult;/));
```

You should not use `case`, `switch`, or `if` statements

```js
assert(
  !/case|switch|if/g.test(code.replace(/([/]{2}.*)|([/][*][^/*]*[*][/])/g, ''))
);
```

# --seed--

## --seed-contents--

```js
// Setup
function phoneticLookup(val) {
  let result = "";

  // Only change code below this line
  switch(val) {
    case "alpha":
      result = "Adams";
      break;
    case "bravo":
      result = "Boston";
      break;
    case "charlie":
      result = "Chicago";
      break;
    case "delta":
      result = "Denver";
      break;
    case "echo":
      result = "Easy";
      break;
    case "foxtrot":
      result = "Frank";
  }

  // Only change code above this line
  return result;
}

phoneticLookup("charlie");
```

# --solutions--

```js
function phoneticLookup(val) {
  let result = "";

  const lookup = {
    alpha: "Adams",
    bravo: "Boston",
    charlie: "Chicago",
    delta: "Denver",
    echo: "Easy",
    foxtrot: "Frank"
  };

  result = lookup[val];

  return result;
}
```
