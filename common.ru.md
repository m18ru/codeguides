# Общие правила оформления кода

Это общие правила по оформлению кода для большинства языков. Эти правила могут быть дополнены или несколько изменены правилами оформления для конкретного языка.

## Отступы и выравнивание

Для отступа всегда должен использоваться символ табуляции — это инклюзивно (размер может быть настроен) и верно семантически (для отступа используется специальный символ). Уровень отступа (количество символов табуляции) должен соответствовать уровню вложенности.

При переносе длинной строки на новую, уровень вложенности увеличивается на один, или выполняется выравнивание (не рекомендуется).

Выравнивание делается только пробелами от текущего уровня отступа, сделанного табуляцией. Использовать табуляции в самом выравнивании запрещено (иначе выравнивание будет ломаться при изменении размера пробела, чего быть не должно).

Использование выравнивания при написании кода крайне не приветствуется, так как это делает строки чрезмерно зависимыми друг от друга, затрудняет правку кода и контроль версий.

Желательно сохранять уровень отступа в том числе и на пустых строках.

Нужно следить, чтобы в используемом редакторе кода при сохранении завершающие строку пробелы не удалялись.

```
// ├──► — Табуляция
// • — Пробел

├──►if•(
├──►├──►(•$a•===•2•)
├──►├──►&&•(•$b•===•3•)
├──►)
├──►{
├──►├──►$c•=•5;
├──►}
├──►
├──►$a•=•array(
├──►├──►'one'•=>•1,
├──►├──►'two'•=>•2,
├──►├──►'three'•=>•3,
├──►);
├──►
├──►// Для функций, которые не помещаются в 80 символов,
├──►// лучше написать каждый аргумент с новой строки
├──►// (здесь иначе для сравнения с выравниванием)
├──►if•(•myfunction(•$var_one,•$var_two,
├──►├──►$var_three,•$var_four•)•)
├──►{
├──►├──►$c•=•2;
├──►}

// Варианты с выравниванием (не рекомендуется)

├──►$a•=•array(
├──►•••••••••••'one'•••=>•1,
├──►•••••••••••'two'•••=>•2,
├──►•••••••••••'three'•=>•3,
├──►);
├──►
├──►if•(•myfunction(•$var_one,•••$var_two,
├──►•••••••••••••••••$var_three,•$var_four•)•)
├──►{
├──►├──►$c•=•2;
├──►}
```

## Максимальная длина строки

Строки кода должны умещаться в 80 символов. В некоторых случаях (например, при большом отступе) допускается длинна строки вплоть до 120 символов. Длиннее 120 символов строка быть не должна.

Если строка не помещается в указанные лимиты и в ней содержится какие било скобки (круглые, квадратные, фигурные), эти скобки «раскрываются», закрывающая скобка переносится на новую строку без отступа, содержимое — с отступом. Обычно, если содержимое представляет перечень, то каждый его элемент записывается с новой строки, но для длинных списков допускается написание в одну строку.

Если строка содержит операторы, то перенос осуществляется на новую строку вместе с оператором (если это допускает синтаксис языка).

```js
if (
	something
	&& ( a === 1 )
	&& (
		isOther()
		|| ( b === 2 )
	)
)

function simple( argument1, argument2 )
{
	// …
}

function some(
	argument1,
	argument2,
	argument3
)
{
	// …
}

function other(
	{
		argument1, argument2, argument3, argument4,
		argument5, argument6,
	}
)
{
	// …
}

const x = calcSome() + someVar
	+ otherVar + 5;

const y = (
	isSome()
	? 1
	: 2
);
```

## Окончания строк

Строки должны завершаться только по стандарту Unix символом перевода строки (LF, `\n`, `0x0A`, символ с кодом 10).
Запрещается использовать символ возврата каретки (CR, `\r`, `0x0D`) или комбинацию символов (Windows‐style, CRLF, `\r\n`, `0x0D+0x0A`).

## Кодировка файлов

Файлы должны быть в кодировке UTF‐8 без использования метки BOM (`EF BB BF`).

Исключением являются случаи, когда нужно создать файл в некоей кодировке в силу определённых обстоятельств, вроде представления данных в нужном виде прямо в файле.

## Расстановка пробелов

Символы операторов отбиваются пробелами, кроме основных унарных:

```js
x = 2 + 3;
b = x === 5;
x += 2;
x++;
x = 5 - -2;
b = !b;
x = b ? 1 : 2;
```

При группировке арифметических операций скобки пробелом не отбиваются, во всех остальных случаях (как логическая группировка, передача аргументов функции) — используется отбивка пробелом. Если функция не содержит аргументов, то между открывающей и закрывающей скобками пробел не ставится.

```js
x = (2 + 3) / 2;
x = round( 2 / 3 ) - 2;
x = ((2 + 3) / 2) + 4;
x = (round( 2 / 3 ) - 2) * 2;
b = ( ( x === 5 ) || ( x === 10 ) );
function myfunction()
myfunction();
myfunction( 1, 2 );
```

Функции и конструкторы не отбиваются от последующей скобки пробелом, а операторы языка должны быть отделены пробелом.

```js
function myfunction( var1, var2 )
myfunction( 1, 2 );
date = new Date();
$a = array();
for ( i = 0; i < 10; i++ )
if ( x === 2 )
```

Комментарии пишутся с отступом в пробел и должны начинаться с заглавной буквы, если не являются продолжением предыдущего. Для комментариев следует использовать именно строчный вариант, блочный используется для документации в коде.

```js
// Comment
x = 1;
// Very long
// comment line
y = 2;
/* Multiline comment */
z = 3;
/**
 * Documentation
 */
a = 4;
/** Single line documentation */
b = 5;
```

## Блок кода

Ограничители блока кода пишутся каждый с новой строки без отступа. Содержимое блока пишется с одинарным отступом.

```js
if ( true )
{
	// …
}
else
{
	// …
}

function some()
{
	// …
}

const f = () =>
{
	// …
}

// Скобки — не ограничитель блока
const f2 = () => (
	// …
);

// В JS фигурные скобки используются не долько для блока — перенос не нужен
const obj = {
	a: 1,
	b: 2,
};
const {a} = obj;
const obj2 = {a: 1};
```

## Вертикальные отступы

Вертикальный отступ в коде должен быть не более одной пустой строки. Если нужно как‐то дополнительно обозначить фрагмент кода, следует воспользоваться комментарием. В начале или конце блока пустой строки быть не должно.

Структурные блоки должны отделяться от кода или других блоков пустой строкой, за исключением случаев, когда это связанные блоки (вроде if…else).

За исключением некоторых отдельных случаев (в силу специфичности или назначения), в конце файла должна быть пустая строка.

```js
someCode();

if ( something )
{
	someCode();
}
else
{
	someOtherCode();
}

someCode();

for ( i = 0; i < 10; i++ )
{
	someCode( i );
}

someCode();

// Пример Switch/Case, он отделён дополнительно с использованием комментария

switch ( i )
{
	case 1:
		codeOne();
		break;
	// ← Этот отступ на уровне case, а не на уровне break
	case 2:
		codeTwo();
		break;
	
	case 3:
	case 4:
		codeThree();
		break;
	
	default:
		codeDefault();
		break;
}
```