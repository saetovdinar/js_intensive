
## 1 task
```js
let promiseTwo = new Promise((resolve, reject) => {
   resolve("a");
});
promiseTwo
.then((res) => {
   return res + "b";// 'ab'
})
.then((res) => {
   return res + "с"; //'abc'
})
.finally((res) => {
   return res + "!!!!!!!"; // ignore
})
.catch((res) => {
   return res + "d"; // ignore
})
.then((res) => {
   console.log(res); //вывод в консоль: abc
});
```

## 2 task
```js
function doSmth() {
   return Promise.resolve("123");
}

doSmth()
.then(function (a) {
   console.log("1", a); //в консоли: 1 123
   return a;
})
.then(function (b) {
   console.log("2", b); //в консоли: 2 123
   return Promise.reject("321");
})
.catch(function (err) {
   console.log("3", err);//в консоли: 3 321
})
.then(function (c) {
   console.log("4", c);//в консоли: 4 undefined
return c;
});
```
## 3 task
1.
```js
function delay(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
  }
  

  function printIndexesWithDelay(arr) {
    let promise = Promise.resolve()
    arr.forEach((element, index) => {
        promise = promise.then(() => {
            console.log(`Index: ${index}, Value: ${element}`);
            return delay(3000);
        })
    });
   
  
    
   
  }
```

2.
```js
function delayPrint(arr) {
    let arrLength = 0;
    let interval;
    if(arr.length > 0) {
        interval = setInterval(() => {
            console.log(arrLength)
            
            arrLength++
            if(arr.length === arrLength) {
                clearInterval(interval)
            }
        }, 500)
    }
   
    
}
```


## 4 task

Await Высшего уровня позволяет использовать await  без оборачивания в асинхронную функцию.
Для этого нужно использовать файлы с расширением mjs в среде node js,
либо скрипт должен быть с указанием типа модуль в браузерной среде выполнения кода.

## 1 bonus
Если я прваильно понял задание: если запрос корректный все блоки catch - игнор, вернет разметку с первой поптыки.
Если запрос не прошел - попытается еще 5 раз и вернет объект промиса с соответсвующим результатом.
```js
function fetchUrl(url) {

    let prom = fetch(url)
    .then(res => res.text())
    .catch(() => {
        return fetch(url)
    })
    .catch(() => {
        return fetch(url)
    })
    .catch(() => {
        return fetch(url)
    })
    .catch(() => {
        return fetch(url)
    })
    
    return prom
}


fetchUrl('https://.google.com/&#')
.then(data => console.log(data))
.catch(err => console.log(err))

```



