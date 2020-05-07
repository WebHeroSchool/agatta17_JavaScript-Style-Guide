# JavaScript Style Guide
## 1. Фигурные скобки
Фигурные скобки обычно пишутся с открывающей скобкой на той же строке, что и соответствующее ключевое слово – не на новой строке. Перед открывающей скобкой должен быть пробел, как здесь:
``` js
if (condition) {
  // делай это
  // ...и это
  // ...и потом это
}
```
В случае однострочной записи допустимо написать код в одну строку без скобок:
``` js
if (n < 0) alert(`Степень ${n} не поддерживается`);
```
Но лучше все-таки со скобками:
``` js
if (n < 0) {
  alert(`Степень ${n} не поддерживается`);
}
```
При записи в одну строку фигурные скобки не нужны. Плохой пример записи:
``` js
if (n < 0) {alert(`Степень ${n} не поддерживается`);}
```
Разделять строки без фигурных скобок не нужно. Как здесь:
``` js
if (n < 0)
  alert(`Степень ${n} не поддерживается`);
```
## 2. Длина строки
Длинные строки лучше разбивать. Например:
``` js
if (
  id === 123 &&
  moonPhase === 'Waning Gibbous' &&
  zodiacSign === 'Libra'
) {
  letTheSorceryBegin();
}
```
Максимальную длину строки согласовывают в команде. Обычно это 80 или 120 символов.
## 3. Отступы
+ Горизонтальные отступы

Отступ при вложенности - 2 пробела на каждый уровень вложенности.
Хорошо:
``` js
if (age < 98) {
  for (var i = 0, iMax = items.length; i < iMax; ++i) {
    // тело цикла
  }
}
```
Плохо:
``` js
if (age < 98) {
for (var i = 0, iMax = items.length; i < iMax; ++i) {
// тело цикла
}
}
```
+ Вертикальные отступы

Между логическими блоками(циклами, функциями и т.д.) следует оставлять пустую строку. Это делает код более читабельным. Избегайте блоков кода более 9 строк подряд.
Хорошо:
``` js
var i;
var iMax = items.length;
for (i = 0; i < iMax, ++i) {
  // тело цикла
}

function showName() {
  // тело функции
}
```
Плохо:
``` js
var i;
var iMax = items.length;

for (i = 0; i < iMax, ++i) {
  // тело цикла
}
function showName() {
  // тело функции
}
```
## 4. Точка с запятой
Точки с запятой должны присутствовать после каждого выражения, даже если их, казалось бы, можно пропустить.
Есть языки, в которых точка с запятой необязательна и редко используется. Однако в JavaScript бывают случаи, когда перенос строки не интерпретируется, как точка с запятой, что может привести к ошибкам.
Хорошо:
``` js
alert('Привет');
alert('Мир');
```
Плохо:
``` js
alert('Привет')
alert('Мир')
```
## 5. Размещение функций
В большинстве случаев предпочтительно сначала размещать код, который использует функции, а затем сами функции. Так как при чтении кода мы сначала хотим знать, что он делает. Если сначала идёт код, то это тут же становится понятно. И тогда, может быть, нам вообще не нужно будет читать функции, особенно если их имена хорошо подобраны.
Хорошо:
``` js
// код, использующий функции
let elem = createElement();
setHandler(elem);
walkAround();

// --- вспомогательные функции ---
function createElement() {
  ...
}

function setHandler(elem) {
  ...
}

function walkAround() {
  ...
}
```
## 6. Создание объектов
Для создания объекта используйте фигурные скобки. Не создавайте объекты через конструктор new Object.
Хорошо:
``` js
var item = {};
```
Плохо:
``` js
var item = new Object();
```
Не используйте зарезервированные и ключевые слова в качестве ключей объектов.
Хорошо:
```js
var superman = {
  defaults: { clark: 'kent' },
  hidden: true
};
```
Плохо:
``` js
var superman = {
  default: { clark: 'kent' },
  private: true
};
```
Плохо:
``` js
var superman = {
  class: 'alien'
};
```
При создании обьектов, равно как и массивов, содержащих большое количество свойств или элементов (3 и более), и тем самым образующих строки, длиной более 20 символов, необходимо выполнять ряд условий:
+ Открывающая скобка располагается на той же строке;
+ Каждое свойство оформляется на новой строке;
+ Пробел после двоеточия;
+ Закрывающая скобка располагается на новой строке.
Хорошо:
``` js
var superman = {
  defaults: { clark: 'kent' },
  type: 'alien',
  hidden: true
};
```
Плохо:
``` js
var superman = {defaults: { clark: 'kent' }, type: 'alien', hidden: true};
```
## 7. Переменные
Для именования переменных используйте существительные на английском языке (не транслит). Имя переменной должно быть осмысленным. Если переменная состоит из нескольких слов, нужно использовать camelCase, когда первое слово пишется с маленькой буквы, остальные с большой.
Хорошо:
``` js
var myGoods;
var price;
var link;
```
Плохо:
``` js
var moitovari;
var cena;
var ssilka;
```
## 8. Функции
Имя функции должно быть глаголом на английском языке или начинаться с него. Для имён, состоящих из нескольких слов, используйте camelCase.
Хорошо:
``` js
function editName() {
  // тело функции
};
```
Плохо:
``` js
function pravkaspiska() {
  // тело функции
};
```
## 9. Кавычки
Всегда в коде скрипта используйте одинарные кавычки, если не требуется иного. Двойные кавычки допустимы, если в этой же строке необходимо использовать апостроф (') или одинарные кавычки для других целей.
Хорошо:
``` js
var string = 'строка';
var phrase = "you're next";
```
Плохо:
``` js
var string = "строка";
```
## 10. Комментарии
Используйте конструкцию /** ... */ для многострочных комментариев.
Хорошо:
``` js
/**
 * make() возвращает новый элемент
 * соответствующий переданному названию тега
 */
function make(tag) {

  // ...

  return element;
}
```
Плохо:
``` js
// make() возвращает новый элемент
// соответствующий переданному названию тега
//
// @param {String} tag
// @return {Element} element
function make(tag) {

  // ...

  return element;
}
```
Используйте двойной слеш // для однострочных комментариев. Располагайте такие комментарии отдельной строкой над кодом, который хотите пояснить. Если комментарий не является первой строкой блока, добавьте сверху пустую строку.
Хорошо:
``` js
// это текущая вкладка
const active = true;
```
``` js
function getType() {
  console.log('fetching type...');

  // установить по умолчанию тип 'no type'
  const type = this.type || 'no type';

  return type;
}
```
``` js
function getType() {
  // установить по умолчанию тип 'no type'
  const type = this.type || 'no type';

  return type;
}
```
Плохо:
``` js
const active = true;  // это текущая вкладка
```
``` js
function getType() {
  console.log('fetching type...');
  // установить по умолчанию тип 'no type'
  const type = this.type || 'no type';

  return type;
}
```
Начинайте все комментарии с пробела, так их проще читать.
Хорошо:
``` js
// это текущая вкладка
const active = true;
```
``` js
/**
 * make() возвращает новый элемент
 * соответствующий переданному названию тега
 */
function make(tag) {

  // ...

  return element;
}
```
Плохо:
``` js
//это текущая вкладка
const active = true;
```
``` js
/**
 *make() возвращает новый элемент
 *соответствующий переданному названию тега
 */
function make(tag) {

  // ...

  return element;
}
```
Если комментарий начинается со слов FIXME или TODO, то это помогает другим разработчикам быстро понять, когда вы хотите указать на проблему, которую надо решить, или когда вы предлагаете решение проблемы, которое надо реализовать. Такие комментарии, в отличие от обычных, побуждают к действию.
Используйте `// FIXME:`, чтобы описать проблему:
``` js
class Calculator extends Abacus {
  constructor() {
    super();

    // FIXME: здесь не должна использоваться глобальная переменная
    total = 0;
  }
}
```
Используйте `// TODO:`, чтобы описать решение проблемы"
``` js
class Calculator extends Abacus {
  constructor() {
    super();

    // TODO: нужна возможность задать total через параметры
    this.total = 0;
  }
}
```

