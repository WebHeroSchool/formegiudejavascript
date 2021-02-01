1. Использовать квадратные скобки [ ] для объявления массивов, потому что массивы-это глобальный объект, который используется для хранения данных.
❌ не надо так 👇

const items = new Array();

✅ надо так 👇

const items = [];

2. Всегда использовать let или const для объявления переменных.
❌ не надо так 👇

uperPower = new SuperPower();
 

✅ надо так 👇

const superPower = new SuperPower();

3. Всегда ставить точку с запятой в конце выражения. Можно, конечно обойтись без точки с запятой, но лучше будет использовать точки с запятой, чтобы избежать подводных камней. Большинство разработчиков их ставят.
❌ не надо так 👇
const luke = {}
const leia = {}
[luke, leia].forEach((jedi) => jedi.father = 'vader')

✅ надо так 👇

const luke = {};
const leia = {};
[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
});

4. Использовать фигурные скобки для всех многострочных блоков.

❌ не надо так 👇

if (test)
  return false;

function foo() { return false; }

✅ надо так 👇

if (test) return false;

function bar() {
  return false;
}

5. Писать каждую пару ключ свойство с новой строки, чтобы был читабельный код и правильная инпретация 
❌ не надо так 👇

const obj0 = { foo: "foo", bar: "bar", baz: "baz" };

const obj1 = {
  foo: "foo", bar: "bar", baz: "baz"
};

✅ надо так 👇

const obj1 = {
  foo: "foo",
  bar: "bar",
  baz: "baz"
};


const user = process.argv[2];
const obj3 = {
  user,
  [process.argv[3] ? "foo" : "bar"]: 0,
  baz: [
    1,
    2,
    4,
    8
  ]
};

6.  Не объявлять функцию внутри цикла.
❌ не надо так 👇

for (let i=10; i; i--) {
  (function() { return i; })();
}


✅ надо так 👇

const a = function() {};

for (let i=10; i; i--) {
  a();
}

7. Использовать стрелочные функции для передачи коллбеков.
❌ не надо так 👇

[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

✅ надо так 👇

[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});

8. Называть функции-конструкторы с большой буквы.

❌ не надо так 👇

const colleague = new person();
const friend = new person.acquaintance();

✅ надо так 👇

const colleague = new Person();
const friend = new person.Acquaintance();

9. Используйте фигурные скобки для создания блоков в case и default в конструкции switch...case , которые содержат лексические объявления (например, let, const, function и class). Лексические объявления видны во всем блоке switch, но инициализируются только при срабатывании определенного case. Чтобы убедиться, что лексическое объявление применяется только к текущему case, необходимо использовать скобки.

❌ не надо так 👇

switch (foo) {
  case 1:
    let x = 1;
    break;
  case 2:
    const y = 2;
    break;
  case 3:
    function f() {
      // ...
    }
    break;
  default:
    class C {}
}

✅ надо так 👇

switch (foo) {
  case 1: {
    let x = 1;
    break;
  }
  case 2: {
    const y = 2;
    break;
  }
  case 3: {
    function f() {
      // ...
    }
    break;
  }
  case 4:
    bar();
    break;
  default: {
    class C {}
  }
}

10. При смешивании операторов заключай их в скобки. Единственным исключением являются стандартные арифметические операторы: +, - и **, так как их приоритет широко понят. Рекомендуется заключать в скобки / и *, потому что их приоритет может быть неоднозначным, когда они смешаны.

❌ не надо так 👇

const foo = a && b < 0 || c > 0 || d + 1 === 0;
const bar = a ** b - 5 % d;

if (a || b && c) {
  return d;
}

const bar = a + b / c * d;

✅ надо так 👇

const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

const bar = a ** b - (5 % d);

if (a || (b && c)) {
  return d;
}

const bar = a + (b / c) * d;