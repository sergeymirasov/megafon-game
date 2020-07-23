# [Megafon Game](https://megafon.geecko.ru)

Игра для кодеров, тестеров, аналитиков и девопсов, выходящая за границы виртуального.

Размести свое послание на билборде в центре Нижнего Новгорода.

Пройди три задания. За каждое задание в конце первых трех глав можно получить от 0 до 100%.

Набери не менее 80%. Как среднее значение трех рейтинговых заданий.

# Задания и ответы на них

> Список ответов будет пополняться!

Возможные условия:

- Герой - `Багмэн`
- Специализация - `Разработчик`
- Язык - `JavaScript`
- Опыт владения - `1-3 года`
- Хотите работать в МегаФоне? - `Нет :)`

### Задание №1

Разгадай шифр пятнистого!

Шифр у него не самый сложный, поэтому думаю ты легко справишься, удачи!

Напиши функцию которая принимает положительное число и возвращает значение «Password is X», где X — переданное число, дополненное нулями до 5 цифр.

Пример:
```js
stringformat(321) == "Password is 00321"
```

<b>Ответы:</b>

<details>
  <summary>Codepen</summary>
  
  [Megafon Game #1](https://codepen.io/newbornfrontender/pen/GRozmOP)
</details>

<details>
  <summary>Пример кода</summary>
  
```js
const text = (n) => `Password is ${n}`;

const stringFormat = (n) => {
  if (String(n).length >= 5) return text(n);
  return text(`0000${n}`.slice(-5));
};
```
</details>

<br />

### Задание №2

Пятнистый череп снова наломал дров. Помоги Мегафонмену, придумай решение задачи.

Дано целое число n. Необходимо вычислить последнюю цифру n-го числа последовательности, заданной следующим соотношением:  

- F0 = 0
- F1 = 1
- Fn = F(n-1) + F(n−2) при n >= 2

<b>Ответы:</b>

<details>
  <summary>Codepen</summary>
  
  [Megafon Game #2](https://codepen.io/newbornfrontender/pen/mdVvmgg)
</details>

<details>
  <summary>Пример кода</summary>
  
```js
const lastDigit = (n) => {
  let a = 1;
  let b = 1;
  let c;
  let i = 2;

  while (i < n) {
    c = (a + b) % 10;
    a = b;
    b = c;
    i = i + 1;
  }

  return b;
};
```
</details>

<br />

### Задание №3

Вы почти починили лифт, но сбилась система расписания лифта с другими лифтами здания, системой обслуживания и тд. Вы не можете просто так это оставить, иначе потом пострадают люди, если лифт запустится не в свое время, например, когда все думают, что идет тех. обслуживание.

Поэтому ваша задача написать функцию `checkAvailability` которая принимает 2 аргумента:  

`schedule` - расписание занятости в формате "hh:mm-hh:mm" 24-h.  Расписание в виде массива строк, состоящих из времени начала и конца временного отрезка, разделенных "-" (Например, `["09:30-10:15"]`).

currentTime - строка с определенным временем в формате hh:mm 24-h, для которой функция будет проверять доступность на основе расписания.

Если во время currentTime  не запланировано никаких работ с лифтом(есть свободный временной слот), функция должна возвращать строку "available". 
Если в currentTime уже занято, функция должна возвращать строку с временем, когда будет доступно.  

Если время, переданное в качестве входных данных, равно времени окончания, функция также должна возвращать значение "available".

Примеры:

```js
checkAvailability(["09:30-10:15", "12:20-15:50"], "11:00") --> "available"
```
```js
checkAvailability(["09:30-10:15", "12:20-15:50"], "10:00") --> "10:15"
```

<b>Ответы:</b>

<details>
  <summary>Codepen</summary>
  
  [Megafon Game #3](https://codepen.io/newbornfrontender/pen/XWXOgXZ)
</details>

<details>
  <summary>Пример кода</summary>
  
```js
const splitRange = (range) => range.split('-');

const isInRange = (value, range) => {
  return value >= range[0] && value <= range[1] ? range[1] : 'available';
};

const checkAvailability = (schedule, currentTime) => {
  const isEqual = splitRange(schedule[0])[1] === splitRange(schedule[1])[0];
  
  if (isEqual) return splitRange(schedule[1])[1];
  
  const result = schedule.map((range) => isInRange(currentTime, splitRange(range)));
  const isAvailable = result.every(value => value === 'available');
  const time = result.filter(value => value !== 'available')[0];
    
  return isAvailable ? 'available' : time;
};
```
</details>

## ToDo

Обязательные для прохождения сюжета:

- [x] Добавить решение для 1 главы
- [x] Добавить решение для 2 главы
- [x] Добавить решение для 3 главы
- [ ] Добавить решение для эпилога

Обязательные для устройства в Megafon:

- [ ] Добавить решение для 4 главы

## License

Данные ответы к заданиям и говнокод являются интеллектуальной собственностью [Sergey Mirasov](https://github.com/sergeymirasov) и опубликованы с ознакомительной целью. Всем добра.

[MIT](/LICENSE) @ [Sergey Mirasov](https://github.com/sergeymirasov)
