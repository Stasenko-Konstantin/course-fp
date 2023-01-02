# Шпаргалка

### Части абстрактного синтаксиса:

- `f` - имя функции
- `x` - параметр функции
- `num` - число
- `var` - переменная
- `expr` - любое допустимое выражение*
- `stmt` - любой допустимый набор инструкций*
- `cond` - любое допустимое булевское выражение
- `...` - возможное повторение предыдущего элемента произвольное кол-во раз

| Expr                                 | Python                                                                                                                                             | Racket                                                                                  |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Арифметика                           | `num` + `num` + `num` `...`                                                                                                                        | (+ `num` `num` `num` `...`)                                                             |
| Глобальное <br>присваивание          | `var` = `expr`                                                                                                                                     | (define `var` `expr`)                                                                   |
| Локальное <br>присваивание**         | `var` = `expr`                                                                                                                                     | (let ([`var` `expr`] `...`)<br>&nbsp;&nbsp;`expr`)                                      |
| Объявление<br>функции                | def `f`(`x`, `...`):<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt`                                                                                             | (define (`f` `x` `...`)<br>&nbsp;&nbsp;`expr`<br>&nbsp;&nbsp;`...`)                     |
| Лямбды                               | lambda `x`, `...`: `expr`                                                                                                                          | (lambda (`x` `...`) `expr` `...`)                                                       |
| Вызов функции                        | f(x)                                                                                                                                               | (f x)                                                                                   |
| Истина                               | True                                                                                                                                               | #t                                                                                      |
| Ложь                                 | False                                                                                                                                              | #f                                                                                      |
| И                                    | `cond` and `cond`                                                                                                                                  | (and `cond` `...`)                                                                      |
| ИЛИ                                  | `cond` or `cond`                                                                                                                                   | (or `cond` `...`)                                                                       |
| НЕ                                   | not `cond`                                                                                                                                         | (not `cond` `...`)                                                                      |
| Последовательный<br>набор инструкций | `stmt`                                                                                                                                             | (begin<br>&nbsp;&nbsp;`expr`<br>&nbsp;&nbsp;`...`)                                      |
| Условное<br>ветвление                | if `cond`:<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt`<br>else:<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt`                                                            | (if `cond`<br>&nbsp;&nbsp;`expr`<br>&nbsp;&nbsp;`expr`)                                 |
| Условное<br>ветвление                | if `cond`:<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt`<br>elif `cond`:<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt`<br>`...`<br>else:<br>&nbsp;&nbsp;&nbsp;&nbsp;`stmt` | (cond<br>&nbsp;&nbsp;[`cond` `expr`]<br>&nbsp;&nbsp;`...`<br>&nbsp;&nbsp;[else `expr`]) |

_*_ [Обсуждение на stackoverflow](https://stackoverflow.com/questions/4728073/what-is-the-difference-between-an-expression-and-a-statement-in-python)
о разнице между выражениями и инструкциями, как раз применительно к Python, на английском. И [документация Racket](https://docs.racket-lang.org/guide/syntax-overview.html)
по этому же вопросу, тоже на английском. <br>
_**_ Переменные доступные в теле функции. В случае Racket объявленные в `let` переменные доступны только в теле этого
самого `let`, т.е. в `expr`. <br>

[содержание](../README.md)
<br>
[назад](../README.md)
<br>
[дальше](l_0/README.md)