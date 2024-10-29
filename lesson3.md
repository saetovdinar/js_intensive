
## 1 task
1. `const counter = {}`
2. `const counter = new Object()`
3. `const counter = Object.create(null)`
4. `const counter = Object.assign({}, {})` - (возможный теоритически, менее удобный, созданный для копирования вариант)

5. С помощью функции Конструктора.
```js
  function Counter(count) {
    this.count = count;`
  }

  `const counter = new Counter('Alice', 30);`
```
6. С помощью обычной функции.
```js
function createCounter( count) {
    return {
        count,
        countIncrem() {
            console.log(this.count++)
        }
    };
}

const counter = createCounter(30);
```
7. С помощью класса.
```js
class Counter {
    constructor(count) {
      this.count = count;
    }
    countIncrem() {
      console.log(this.count++)
    }
}

const counter = new Counter(30);
```

## 2 task
```js
const counter = {
  count: 30,
  countIncrem() {
    this.count++
  }
}
```
Поверхностные копии: 

1. `const counterCopy = Object.assign({}, counter) `
2. `const counterCopy = {...counter}`
3. `for in`
```js
const copy = {};

for(let key in counter) {
    copy[key] = counter[key];
}
```
Глубокие копии

1. `const counterCopy = JSON.parse(JSON.stringify(counter))`; (есть минусы с undefined, Date  и цикилческими ссылками объектов)
2. Библиотеки
```js
  const lodash = require('lodash');
  const counterCopy = lodash.cloneDeep(counter);
```
3. `const copy = structuredClone(counter)`


4. Ручное копирование 
```js
function deepCopy(arg) {
    if (arg === null || typeof arg !== 'object') return arg;
    if(Array.isArray(arg)) return arg.map(deepCopy)

    const copy = {};
    for (const key in arg) {
      copy[key] = deepCopy(arg[key]);
    }
    return copy;
}


```


## 3 task
1. `function makeCounter() {}`
2. `const makeCounter  = function() {}`
3. `const makeCounter = () => {}`
4. `function MakeCounter () {}`
5. `const makeCounter  = function make() {}`
6. IIFE
```js
(function makeCounter() {
    console.log();
})();
```
7. Cоздание внутри функции высшего порядка
```js
function make() {
  return function makeCounter() {}
}
```



## 4 task
`structuredClone(obj)` - глобальный метод, выполняющий глубокое копирование объектов. Корректно работает с undefined, Date, 
цикилческие ссылки объектов.



## 1 bonus
```js
const deepEqual =(arg1, arg2) => {
    if(typeof arg1 !== 'object' || typeof arg2 !== 'object')return arg1 === arg2;  
    if(arg1 === arg2) return true;
    if(Array.isArray(arg1)) return arg1.map((el, i) => deepEqual(el, arg2[i])).every(el => el === true);

    for(const key in arg1) {
        if(!deepEqual(arg1[key], arg2[key])) return false;
    }


    return true;
};
```



## 2 bonus
```js
function reverseStr(str) {
    return str.split("").reverse().join("");
}
```