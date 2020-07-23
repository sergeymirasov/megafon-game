# [Megafon Game](https://megafon.geecko.ru)

Игра для кодеров, тестеров, аналитиков и девопсов, выходящая за границы виртуального.

Размести свое послание на билборде в центре Нижнего Новгорода.

Пройди три задания. За каждое задание в конце первых трех глав можно получить от 0 до 100%.

Набери не менее 80%. Как среднее значение трех рейтинговых заданий.

# Задания и ответы на них

> Список ответов будет пополняться!

### Задание № 1

Разгадай шифр пятнистого!

Шифр у него не самый сложный, поэтому думаю ты легко справишься, удачи!

Напиши функцию которая принимает положительное число и возвращает значение «Password is X», где X — переданное число, дополненное нулями до 5 цифр.

Пример:
```js
stringformat(321) == "Password is 00321"
```

Ответы:
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

## ToDo

Обязательные для прохождения сюжета:

- [x] Добавить решение 1 задания
- [ ] Добавить решение 2 задания
- [ ] Добавить решение 3 задания

Обязательные для устройства в Megafon:

- [ ] Добавить решение 1 задания

## License

Данные ответы к заданиям и говнокод являются интеллектуальной собственностью [Sergey Mirasov](https://github.com/sergeymirasov) и опубликованы с ознакомительной целью. Всем добра.

[MIT](/LICENSE) @ Sergey Mirasov
