
## 1 task
Признаки "непраильного" поведения массивов
1. В JS маассивы могут хранить разные типы данных , что отличает их от других языков и могут 
привести к небольшим путаницам
2. К массивам можно добавлять свойства и методы, что копирует поведение объектов.
3. Они могут вести себя как стеки и очереди.(pop, push, shift, unshift)
4. Могут вести себя как матрицы
5. Отсутсвие фиксированного размера


## 2 task
```js
function logger() {
    console.log(`I output only external context: ${this.item}`);
}

const obj = { item: "some value" };
```
Решение
```js
logger.call(obj)
logger.apply(obj)

const bindedLogger = logger.bind(obj)
bindedLogger()
```


## 3.1 task

```js
1.
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

arr.reduce((accum, item) => {
    return accum + item
}, 0)
2.
let arr = ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10'];

arr.reduce((accum, item) => {
    return accum + item
}, '');


3. let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
Math.max(...arr)
Math.min(...arr)

```




## 3.2 task

Stack
```js
let arr = [];
let elem = 0;
function addElemToStack() {
    arr.push(elem);
    console.log(arr);
    elem++;
}

function removeElemFromStack() {
    arr.pop();
    console.log(arr);
}

setInterval(addElemToStack, 500);
setInterval(removeElemFromStack, 1000);

```
## 3.3 task
Queue 
```js
let arr = [];
let elem = 0;
function addElemToStack() {
    arr.unshift(elem);
    console.log(arr);
    elem++;
}

function removeElemFromStack() {
    arr.pop();
    console.log(arr);
}

setInterval(addElemToStack, 500);
setInterval(removeElemFromStack, 1000);
```
## 1 bonus
```js
 function copyBind(context, func, ...args) {
    return function () {
        
        context.binded = func
         
        context.binded(...args)
    }
}
```








