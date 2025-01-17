```javascript
const a = Symbol();
const b = Symbol();

const c = Symbol('c');
const d = Symbol('c');
const e = Symbol('e');

// Symbol 的参数是一个对象，就会调用该对象的toString()方法，将其转为字符串，然后才生成一个 Symbol 值
const obj = {
  toString() {
    return 'abc';
  }
};
const sym = Symbol(obj);
sym // Symbol(abc)

typeof sl // Symbol
console.log(c); // Symbol(c);
c.toString() // "Symbol(c)"

a === b // false
c === d // false

// Symbol 值不能与其他类型的值进行运算
"your symbol is " + c // TypeError: can't convert symbol to string

// Symbol 值可以显式转为字符串。
String(c) // 'Symbol(c)'
c.toString() // 'Symbol(c)'

// 可以转为布尔值，但是不能转为数值
Boolean(c) // true
!c  // false
Number(c) // TypeError
c + 2 // TypeError

c.description // "c"


let s1 = Symbol.for('foo');
let s2 = Symbol.for('foo');

s1 === s2 // true
// Symbol.keyFor()方法返回一个已登记的 Symbol 类型值的key   
Symbol.keyFor(s1) // "foo" 
```

Symbol 值作为属性名，遍历对象的时候，该属性不会出现在for...in、for...of循环中，也不会被Object.keys()、Object.getOwnPropertyNames()、JSON.stringify()返回。有一个Object.getOwnPropertySymbols()方法，可以获取指定对象的所有 Symbol 属性名

```js
const obj = {};
let a = Symbol('a');
let b = Symbol('b');

obj[a] = 'Hello';
obj[b] = 'World';

const objectSymbols = Object.getOwnPropertySymbols(obj);

objectSymbols
// [Symbol(a), Symbol(b)]
```