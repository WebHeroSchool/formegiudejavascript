1. Не используовать множественное присваивание. Такие конструкции создают неявные глобальные переменные.
❌ не надо так 👇

(function example() {
  let a = b = c = 1;
}());
console.log(a); // ошибка ReferenceError
console.log(b); // 1
console.log(c); // 1
✅ надо так 👇

(function example() {
  let a = 1;
  let b = a;
  let c = a;
}());
console.log(a); // ошибка ReferenceError
console.log(b); // ошибка ReferenceError
console.log(c); // ошибка ReferenceError

2. Использовать let и const для объявления каждой переменной.
❌ не надо так 👇

const name = getItems(),
    window = true,
    dragonball = 'z';

    ✅ надо так 👇

const name = getItems();
const window = true;
const dragonball = 'z';

3. Не переносить строку после опретора присваивания 

❌ не надо так 👇

const foo =
  superLongLongLongLongLongLongLongLongFunctionName();

  ✅ надо так 👇

const foo = (
  superLongLongLongLongLongLongLongLongFunctionName()
);

const foo = 'superLongLongLongLongLongLongLongLongString';

4. Не объявлять неиспользуемые переменные

❌ не надо так 👇

let x = 0;
let y = 1; // Переменная не используется

function getX() {
    return x + 1;
}

✅ надо так 👇

let x = 0;

function getX() {
    return x + 1;
}

5. Запятые не должны быть в начале строки 
❌ не надо так 👇

const story = [
    once
  , upon
  , aTime
];

✅ надо так 👇

const story = [
  once,
  upon,
  aTime,
];

6. Всегда ставить точку запятой в конце предложения

❌ не надо так 👇
// Выбросит исключение
const luke = {}
const leia = {}
[luke, leia].forEach((jedi) => jedi.father = 'vader')

✅ надо так 👇
const luke = {};
const leia = {};
[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
});

7. Использовать фигурные скобки для многострочных блоков

❌ не надо так 👇

if (test)
  return false;

function foo() { return false; }

✅ надо так 👇

if (test) return false;

function bar() {
  return false;
}

8. При использовании конструкции if .. else располагайте else на одной строке со скобкой закрывающей блок if.

❌ не надо так 👇

if (test) {
  thing1();
  thing2();
}
else {
  thing3();
}

✅ надо так 👇

if (test) {
  thing1();
  thing2();
} else {
  thing3();
}

9. Для объявления объекта использую фигурные скобки.

❌ не надо так 👇

const item = new Object();

✅ надо так 👇

const item = {};

10. Не дублируй названия ключей в объектах.

❌ не надо так 👇

var foo = {
    bar: "baz",
    bar: "qux"
};

var foo = {
    "bar": "baz",
    bar: "qux"
};

✅ надо так 👇

var foo = {
    bar: "baz",
    quxx: "qux"
};