# Examples of everything new in ECMAScript 2016, 2017, and 2018

[Reference](https://medium.freecodecamp.org/here-are-examples-of-everything-new-in-ecmascript-2016-2017-and-2018-d52fa3b5a70e)

## ES 2016  

1.  Array.prototype.includes

- Help to find if an item is in the array.

```js
const ARRAY = [1, 3, 5, 7];
ARRAY.includes(3);
```

2.  Exponentiation infix operator

```js
// old
Math.pow(2, 3);
// new
2 ** 3;
```

3.  Spread Operator (...)

- Give you ability to expand or spread iterable object into multiple elements.

```js
// Conbine two arrays
const fruits = ["blue berry", "bannan", "pear"];
const vegetables = ["carrot", "corn", "potato"];

// Pre-ES6
const result = fruits.concat(vegetables);

// ES6 with spread Operator
const newResult = [...fruits, ...vegetables];
```

```js
// Expand Array
const numbers = [1, 3, 5, 7, 9];
console.log(...numbers); //1,3,5,7,9
```

## ES 2017

1.  Object.values()

```js
const CARS = { BMW: 2, Tesla: 1 };
//ES5
const VALS = Object.keys(CARS).map(key => CARS[key]); //[2,1]

//ES7
const RESULT = Object.values(CARS);
```

2.  String padding  
    12 => 0012
    1 => 0001

```js
"12".padStart(4, 0); //0012
"1".padStart(4, 0); //0001

"12".padEnd(4, 0); //1200
"1".padEnd(4, 0); //1000
```

3.  Async/Await  
    To deal with callback hell and make entire code more simple.

```js
//ES5 Promise
function getAmount(userId) {
  getUser(userId)
    .then(getBalance)
    .then(amount => {
      console.log(amount);
    });
}

//ES8 ES2017
async function getAmount(userId) {
  var user = await getUser(userId);
  var amount = await getBalance(user);
  console.log(amount);
}
```

Async function themseleves return a **promise**. Therefore, if you are waiting the result from async function, you need to use Prmose's **then** syntax to capture the result.

```js
async function doubleAndAdd(a, b) {
  a = await doubleNumber(a);
  b = await doubleNumber(b);
  return a + b;
}

doubleAndAdd(1, 2).then(console.log);

function doubleNumber(num) {
  return new Promise(resolve => {
    resolve(num * 2);
  });
}
```
