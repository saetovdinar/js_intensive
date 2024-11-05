
## 1 task

Быстрая сортировка (Quick Sort)
Сортировка слиянием (Merge Sort)
Сортировка вставками (Insertion Sort)
Сортировка выбором (Selection Sort)
Сортировка пузырьком (Bubble Sort)
Сортировка кучей (Heap Sort)
Тимсорт (Tim Sort)
Сортировка по подсчету (Counting Sort)
## 3 task
1.
```js
class Person {
    constructor(name, age) {
      this.name = name
      this.age = age
    }
    showName() {
      console.log(this.name)
    }
    doubleAge() {
      this.age *= 2;
    }
}
class Person2 extends Person {
    constructor(name, age, gender) {
      super(name, age)
      this.gender = gender
    }
    showName() {
        super.showName()
        console.log(this.name)
    }
    tripleAge() {
      this.age *= 3;
    }
}

Person.prototype.logInfo = function() {
    console.log(this.name, this.age)
}
```

2.
```js
function Person(name, age) {
    this.name = name
    this.age = age
}

Person.prototype.logInfo = function() {
    console.log(this.name, this.age)
}
Person.prototype.showName = function() {
    console.log(this.name)
}
Person.prototype.doubleAge = function() {
    this.age *= 2
}
function Person2(name, age, gender) {
    this.name = name
    this.age = age
    this.gender = gender
}

Person2.prototype = Object.create(Person.prototype)
Person2.prototype.constructor = Person2

```


## 4 task
```js
class Person {
    constructor(name, age) {
      this.name = name
      this.age = age
    }
    showName() {
      console.log(this.name)
    }
    doubleAge() {
      this.age *= 2;
    }
}
class PersonThree extends Person {
    constructor(name, age, gender) {
      super(name, age)
      this.gender = gender
    }
    
    get name() {
        return this._name
      }
    set name(name) {
        this._name = name
    }
    showName() {
      super.showName()
      console.log(this.name)
    }
    tripleAge() {
      this.age *= 3;
    }
}

```


## 1 bonus
```js
function firstSum (arr, total) {
    let storage = new Set();

    for (let i = 0; i < arr.length; i++) {
        let current = arr[i];
        let needed = total - current;
        if (storage.has(needed)) {
            return [needed, current];
        }
        storage.add(current);
    }
    return 'таких нет'
}

сложность в худшем случае - O(n)

----------------------------
ответ [4, 9] получим если пройдемся двойным циклом, 
время будет O(n^2) - экспоненциальная нагрузка
```



