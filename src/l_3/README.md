# Знакомство с рекурсией
Наверняка когда вы слышите слово "рекурсия" у вас всплывает в голове нечто такое:

![](../../img/l_3/1.png)

Нечто до бесконечности вложенное само в себя. И это равнозначно итерации с которой вы уже должны быть 
знакомы. Итерирование я бы представил зацикленной гифкой. Давайте теперь посмотрим как это выглядит в коде:

```python
# python - итерирование
i = 0
while True:
    print(i)
    i += 1
```
```racket
; racket - итерирование
(let ([i 0])
  (for ([loop (in-naturals)])
    (displayln i)
    (set! i (+ i 1))))
```

Подобное поведение можно представить и через рекурсивные функции, т.е. функции определяемые через 
самих себя:

```python
# python - рекурсия
# не запускайте
i = 0
def infInc():
    global i
    print(i)
    i += 1
    infInc()
infInc()
```
[//]: # (TODO: y-комбинатор)
```racket
; racket - рекурсия
; не запускайте
(let* ([i 0]
       [inf-inc
        (λ ()
          (begin
            (displayln i)
            (set! i (+ i 1))
            (inf-inc)))])
  (inf-inc))
```

Этот код выполняет ровно ту же самую работу, что и примеры с циклами выше. Вместо итераций цикла
мы имеем вызов функции. Все эти примеры будут выполняться бесконечно (на что намекает название функций),
что зачастую бесполезно (если конечно вы не пишите сервера, GUI-фреймворк или игровой движок),
поэтому и цикл, и рекурсию можно прервать. Давайте разберем наиболее частые примеры использования 
циклов с эквивалентными примерами переписанными через рекурсию. 

```python
# python - обход коллекции с помощью цикла
list = [1, 2, 3]
for i in list:
    print(i)
```
```scala
// scala - обход коллекции с помощью цикла
val list = List(1, 2, 3)
for i <- list do
  println(i)
```
```python
# python - обход коллекции с помощью рекурсии
def printList(list):
    if list == []:
        return
    print(list[0])
    printList(list[1:])
printList([1, 2, 3])
```
```scala
// scala - обход коллекции с помощью рекурсии
def printList(list: List[Int]): Unit = list match
  case head::tail => println(head); printList(tail)
  case Nil => return;
printList(List(1, 2, 3))
```

Если раньше особых преимуществ Scala перед Python было не видно, то теперь думаю понятно почему
нужно было использовать два языка. В данном примере 