/////////////////////////////////////////////////////////////////////////
1 task 
1. const counter = {}
2. const counter = new Object()
3. const counter = 





/////////////////////////////////////////////////////////////////////////
2 task
Ключевая особенность - использование QUIC транспортного протокола вместо TPC.
Что способствует установлению более быстрого соединению сетей и улучшению производительности



/////////////////////////////////////////////////////////////////////////
3 task 
1. XMLHttpRequest предлагает метод - abort()
2. Fetch API предлагает класс AbortController
const controller = new AbortController();
const signal = controller.signal;

fetch("url", { signal })
  .then(response => {
    // Обработка ответа
  })
  .catch(err => {
    if (err.name === 'AbortError') {
      console.log('Запрос отменён');
    }
  });

// Отмена запроса
controller.abort();
3. Axios предлагает встроенный класс CancelToken, 
при создании экзепляра которго коллбек принимает аргумент-функцию,
с помощью которой можно отменить запрос.


/////////////////////////////////////////////////////////////////////////
4 task

1. 
- const str = String(23);
- const str = 'Hello';
- const str = "Hello";
- const str = `Hello`;
- const str = `Hello` + 12;
- const str = parseInt('12');

2.
- onst num = Number('23');
- const num = 23;
- const num = +'12';
3.
- const boolean = true;
- const boolean = Boolean(2);
- const boolean = !!1
4.
- const null = null;
5.
- const undef = undefined;
- var undef;
6. 
- const symbol = Symbol("12");
7. 
- const bigInt = 12n;
- const bigInt = BigInt(12);



/////////////////////////////////////////////////////////////////////////
5 task

Переменные данного типа поддерживают Hoisting, но в отличие от var, 
которому присваевается значение undefined, уходят в TDZ и не получают значения.
Вследствии чего , при обращении до инициализации, мы получаем ошибку.



/////////////////////////////////////////////////////////////////////////
6 task

const res = "B" + "a" + (1 - "hello");
console.log(res); //BaNaN

const res2 = (true && 3) + "d";
console.log(res2); //3d

const res3 = Boolean(true && 3) + "d";
console.log(res3); //trued