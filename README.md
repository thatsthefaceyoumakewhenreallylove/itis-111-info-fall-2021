# Курс "Информатика и программирование"

# Информация

- Фамилия Имя Отчество
- группа
- языки программирования, которые вы знаете
- что ещё вы хотите сообщить

# Домашние задания

## 1

Программа `P1.java` из моего репозитория

## 2

Человек загадывает число от 0 до 1023 (включительно).

Компьютер спрашивает, больше или меньше загаданное
указанного числа. Чтобы спросить, больше или меньше числа X,
вывести "? X", например, "? 512"

Ответ 0 означает "меньше", ответ 1 - "не меньше".

Программа должна вывести ответ в виду "! X", например,
"! 123"

Для того, чтобы не переводить строку в конце вывода,
используйте System.out.print. Также можно использовать
конструкцию вида System.out.println("! " + x)

## 3 

Вводится целое положительное N.
Вывести YES, если N - простое, NO - если составное.

Простое число - ровно два делителя (1 и само число).

Число N простое - если оно не делится ни на одно число от 2 до N-1 и N > 1.

```
47
YES 
======
49
NO 
======
1 
NO
```

## 4

Вводится число N.
Вывести первые N простых чисел

```
10 
2 3 5 7 11 13 17 19 23 29
```

## 5

Вводятся целые числа, ввод завершается 0.

Вывести сумму чисел между первым числом, равным максимальному, и вторым числом, равным максимальному.

``` text
1 2 3 2 3 1 1 1 3 -1 0
2

0
NO
```

## 6

Вводятся целые числа, ввод завершается 0.

Вывести сумму чисел между первым максимальным и последним минимальным, включая сами минимум и максимум

``` text
1 3 2 3 -1 2 -1 1 2 0
8
---
-1 1 2 3 0
0
```

## 7

Вводится x.

``` text
 inf
-----
\       (-1)^k x^(2k+1)
<      -----------------
/           (2k+1)!
-----
 k=0
```

Вывести sin x по формуле с точностью 10^{-6}

## 8

Вводится n.

Заполнить и вывести (через `Arrays.toString`) массивы:
- в обратном порядке, начиная с n
- элементы на четных индексах возрастают, 
  на нечётных убывают (от 1 до n)

Код заполнения должен выглядеть так:

``` java
Scanner sc = new Scanner(System.in);
int n = sc.nextInt();
int[] a = new int[n];
int[] b = new int[n];
for (int i=0; i<n; i++) {
  int k1 = i; // можно менять эту строку
  a[k1] = i+1; // первый массив
  int k2 = i; // можно менять эту строку
  b[k2] = i+1; // второй массив
}
System.out.println(Arrays.toString(a));
System.out.println(Arrays.toString(b));
```

```
5
[5, 4, 3, 2, 1]
[1, 5, 2, 4, 3]
```

```
6
[6, 5, 4, 3, 2, 1]
[1, 6, 2, 5, 3, 4]
```


## 9

Вводятся целые числа `N` и `M`.

Заполнить двумерный массив размера `N x M` по спирали, начиная с 1 по часовой стрелке от левого верхнего угла (см. пример).

Вывести его элементы построчно через пробел

```
3 4
-------------
 1  2  3  4
10 11 12  5
 9  8  7  6
=============
4 5
-------------
 1  2  3  4  5
14 15 16 17  6
13 20 19 18  7
12 11 10  9  8
=============
2 2
-------------
1 2
4 3
```

## 10

Клетки на шахматной доске обозначаются парой координат (каждая от 0 до 7).

Вводится `N`.
Вводятся `N` фигур в виде тройки
"вертикаль, горизонталь, вид фигуры" (2 - ладья, 3 - слон).
Вводится `M`.
Вводится `M` клеток в виде пары "вертикаль, горизонталь".

Для каждой клетки вывести `YES`, если она под боем, и `NO`, если нет

Клетка, занятая фигурой считается находящейся под боем.

```
2
1 2 2
6 2 3
3
0 0
7 2
5 3
-------
NO
NO
YES
```

## 11

Написать функцию `int[] carry(int q, int[] a)`, которая выполняет переносы.

В массиве `a` хранятся цифры числа (возможно, превышающие основание `q` системы счисления), в индексе 0 - младшая цифра (например, `12` будет храниться как `a[0] = 2, a[1] = 1`; будем записывать это как `{2,1}`)

Вернуть новый массив, в котором число после выполнения переносов.

```
carry(10, {12,10,7,7,5,4})
---
{2,1,8,7,5,4}
```
потому что выполнили перенос из `12` и дальше из `10+1`.

```
carry(10, {42})
---
{2,4}
```

В последних элементах возвращенного массива могут быть нули. Гарантируется, что входные цифры не будут больше `q*q`. Гарантируется, что результат будет длиннее не более, чем на одну цифру. 

## 12

Написать функцию `int[] multiplyDigit(int q, int[] a, int k)`, которая умножает число `a` на цифру `k` (`0 <= k < q`) в системе счисления с основанием `q` и возвращает полученное число.

```
multiplyDigit(10, {6,5,4,3,2,1}, 3)
---
{8,6,3,0,7,3}
```
потому что `123456 * 3 = 370368`.

```
multiplyDigit(100, {1,2}, 0)
---
{0,0,0}
```

В последних элементах возвращенного массива могут быть нули.

Вы можете использовать функцию выполнения переносов, вызывая её как `P11.carry(...)`. Гарантируется, что она работает так, как указано в предыдущей задаче. Не гарантируется, что эта реализация - ваша.

## 13

Написать функцию `int[] add(int q, int[] a, int[] b)`, которая выполняет сложение двух чисел, записанных в виде массивов цифр `a` и `b` в системе счисления с основанием `q`.

В последних элементах возвращенного массива могут быть нули.

Можно использовать функции `P12.multiplyDigit` и `P11.carry`. Нельзя использовать встроенную в Java длинную арифметику.

```
add(10, [3,2,1], [1,2,3])
[4,4,4]
```

```
add(10, [9,9,9], [1])
[0,0,0,1]
```

```
add(10, [9,9,9], [9,9])
[8,9,0,1]
```

```
add(16, [15,8,4,3], [8,4,3])
[7,13,7,3]
```
