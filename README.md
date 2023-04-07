# js-rampup

## var, let and const
### A. accessibility w.r.t. scope
1. outer var accessible inside scope? -> Yes
```js
var a = 10;
{ 
    var b = a + 10;
}
console.log(b);
// 20
```

2. inner var accessible outside scope? -> Yes
```js
{
    var x = 100;
}
var y = x + 100;
console.log(y);
// 200
```

3. outer let accessible inside scope? -> Yes
```js
let m = 10;
{
    let n = m + 50;
    console.log(n);
}
// 60
```

4. inner let accessible outside scope? -> No
```js
{
    let i = 20;
}
let j = i + 10; 
// ReferenceError: i is not defined
```

5. outer const accessible inside scope? -> Yes
```js
const p = 10;
{
    const q = p + 50;
    console.log(q)
}
// 60
```
6. inner const accessible outside scope? -> No
```js
{
    const t = 20;
}
const u = t + 10; 
// ReferenceError: t is not defined
```

### B. variable reassignability
1. var - can be reassigned (with var)? -> Yes
```js
var a = 10;
var a = 20;
console.log(a);
// 20
```
2. var - can be reassigned (without var)? -> Yes
```js
var a = 10;
a = 20;
console.log(a);
// 20
```
3. let - can be reassigned (with let)? -> No
```js
let a = 10;
let a = 20;
// SyntaxError: Identifier 'a' has already been declared
```
4. let - can be reassigned (without let)? -> Yes
```js
let a = 10;
a = 'home';
console.log(a);
// home
```
5. const - can be reassigned ? -> No
```js
const a = 'party';
a = 'party over';
// TypeError: Assignment to constant variable.
```
6. var - does value change after in-scope reassignment? -> Yes
```js
var a = 10;
{
   a = 'great'; 
}
console.log(a);
// great
```
7. let - does value change after in-scope reassignment? (with let)-> No
```js
let a = 10;
{
   let a = 'great'; 
}
console.log(a);
// 10
```
8. let - does value change after in-scope reassignment? (without let)-> No
```js
let a = 10;
{
   a = 'great'; 
}
console.log(a);
// great
```
9. const - does value change after in-scope reassignment? -> Yes
```js
const a = 10;
{
   a = 'great'; 
}
console.log(a);
// TypeError: Assignment to constant variable.
```
### C. variable hoisting
1. var - can be declared after initializing? -> Yes
```js
a = 10;
var a;
console.log(a)
// 10
```
2. let - can be declared after initializing? -> No
```js
a = 10;
let a;
// ReferenceError: Cannot access 'a' before initialization
```
3. const - no way man
```js
a = 10;
const a;
// ReferenceError: Cannot access 'a' before initialization
```
4. var - can be assigned after declaration? -> Yes
```js
var a;
a = 10;
console.log(a);
// 10
```
5. let - can be assigned after declaration? -> Yes
```js
let a;
a = 10;
console.log(a);
// 10
```
6. const - can be assigned after declaration? -> No
```js
const a;
a = 10;
console.log(a);
// SyntaxError: Missing initializer in const declaration
```
