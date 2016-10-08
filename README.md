# Краткое введение в FSharp


## Особенности программирования на FSharp

 - отступы и пробелы имеют значение при форматировании кода
 - доступно окно интерпретатора, в котором можно выполнить команды
 - язык F# многое взял от **OCaml**
 - доступны типы и библиотека .NET


## Пример использования .NET

```F#
open System

let now = DateTime.Now
```

## Комментарии

```F#
// - однострочный комментарий
(*
 Многострочный комментарий
 (может занимать несколько строк)
*)
```

## REPL

При использовании **MS Visual Studio** можно открыть окно **F# interactive** и вводить команды. Можно выделить в программе текст и послать его в REPL комбинацией: *Alt+Enter*.

Вне *Visual Studio* запустить интерпретатор можно программой *fsi*.

## Стандартные типы

Ниже перечислены основные типы с указанием суффиксов при связывании значений с именами:

- **byte** - _uy_ - беззнаковый байт
- **sbyte** - _y_ - знаковый байт
- **int16** - _s_ - короткое целое
- **uint16** - _us_ - беззнаковое короткое целое
- **int32** - по-умолчанию - обычное целое
- **uint32** - _u_ - беззнаковое целое
- **int64** - _L_ - длинное целое
- **uint64** - _UL_ -  беззнаковое длинное целое
- **float32** - _f_ - вещественное одинарной точности
- **float** - вещественное двойной точности
- **decimal** - _M_ - вещественное фиксированной точности (28 цифр после запятой)

Примеры создания значений:

```F#
let a = 7uy
let b = -18s
let c = 0b1010101y
```

Примеры с возведением в степень:

```F#
> let d = 2UL 56;;
val b : uint64 = 72057594037927936UL
```

## Преобразования типов

Явные преобразования типов необходимы, поскольку в языке отсутствуют неявные преобразования. 

Функции преобразования имеют такие же названия, что и типы, например:

```F#
>let e = uint64 2;;
val e : uint64 = 2UL
```

## Сверхдлинные числа

```F#
>open System.Numerics;;
>let f = 2I ** 200 ;;
val f : BigInteger = 
  16069380442589902755419620923411626.......
```

## Символы и строки

Все символы хранятся в юникоде:

```F#
>let ch = 'л';;
val ch : char = 'л'
> int ch;;
vat it : int = 1083
```

Строки:

```F#
>let hello = "hello, world!";;
val hello : string = "hello, world!"
> hello.[1]
val it : char = 'e'
```

## Функции

Для функционального языка программирования **функция** - центральное понятие.

```F#
>let square = x * x;;
val square : int -> int
>square 2;;
val it : int = 4
```

Функция **square** принимает параметр *int* и возвращает результат типа *int*.

```F#
> let add x y = x + y;;
val add : int -> int -> int
```

В данном случае функция *add* принимает два параметра и возвращает функцию, принимающую один параметр, возвращая, в свою очередь, целое число. 

Можно явно указать типы параметров:

```F#
>let add (x : float) y = x + y;;
val add : float -> float -> float
```

Параметр обобщенного типа:

```F#
>let prn (x : 'a) = x;;
val prn : 'a -> 'a
```

В качестве обобщенного типа может использоваться любой тип. 

















 
