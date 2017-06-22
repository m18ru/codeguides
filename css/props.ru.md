# Правила оформления свойств в файлах CSS

## Общие правила

* Координаты и им подобные значения записываются в порядке x, y, z, сверху-вниз, слева-направо.
* Стороны записываются по часовой стрелки начиная от верха: top, right, bottom, left.
* Свойства, которые имеют заданный порядок в сокращённой форме, в подробной располагаются в этом же порядке.
* Для нулевых значений размерность не указывается (не `0px`, а `0`, кроме случаев, где это необходимо, например `0s`).
* Для дробных чисел ведущий ноль следует всегда писать, так как это очевиднее для восприятия (не `.5em`, а `0.5em`).
* Где возможно, позиция записывается словами (не `50% 0`, а `center top`).
* Для line-height размерность не указывается, если он выставляется относительно текста.
* При указании шрифта всегда должно быть указано его семейство (`"Arial", sans‐serif`).
* Крайне нежелательно прописывать вручную свойства с вендорными префиксами — лучше оставить это на обработку препроцессорам.
* Модификатор `!important` не должен использоваться.

## Порядок свойств

Блоки разделяются пустой строкой. Комментарий с названием блока не требуется.

```css
.just-ignore-this-string {

/* Позиционирование */
position: absolute;
top: 0;
right: 0;
bottom: 0;
left: 0;
z-index: 1;

/* Форматирование блока */
display: block;
flex-flow: row wrap;
flex-direction: row;
flex-wrap: wrap;
justify-content: flex-start;
align-items: stretch;
align-content: stretch;
align-self: auto;
order: 0;
float: left;
shape-outside: url("images/shape.png");
shape-image-threshold: 0.5;
shape-margin: 10px;
clear: both;
box-decoration-break: clone;
overflow: hidden;
overflow-x: hidden;
overflow-y: hidden;
clip: rect(0, 0, 10px, 10px);
clip-path: url("images/resources.svg#clip1");
mask: url("images/resources.svg#mask1");
mask-type: luminance;
visibility: visible;

/* Макет (размеры блока) */
box-sizing: border-box;
flex: 1 1 20%;
flex-grow: 1;
flex-shrink: 1;
flex-basis: 20%;
width: auto;
min-width: 0;
max-width: none;
height: auto;
min-height: 0;
max-height: none;
padding: 0 0 0 0;
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 0;
margin: 0 0 0 0;
margin-top: 0;
margin-right: 0;
margin-bottom: 0;
margin-left: 0;

/* Шрифт и форматирование текста */
font: italic bold 12px/2 Arial, sans-serif;
font-family: Arial, sans-serif;
font-size: 12px;
font-size-adjust: none;
font-style: italic;
font-stretch: condensed;
font-variant: small-caps;
font-variant-alternates: historical-forms;
font-variant-caps: small-caps;
font-variant-east-asian: normal;
font-variant-ligatures: contextual discretionary-ligatures common-ligatures;
font-variant-numeric: ordinal;
font-variant-position: super;
font-weight: bold;
font-kerning: auto;
font-synthesis: weight style;
font-feature-settings: normal;
font-language-override: "RUS";
line-height: 2;
letter-spacing: 0.05em;
word-spacing: normal;
white-space: nowrap;
word-break: break-all;
word-wrap: break-word;
overflow-wrap: break-word;
line-break: auto;
hyphens: manual;
tab-size: 4;
text-align: justify;
text-align-last: left;
text-decoration: underline;
text-decoration-line: underline;
text-decoration-color: red;
text-decoration-style: wavy;
text-underline-position: under;
text-indent: 1.5em;
text-overflow: ellipsis;
text-rendering: optimizeLegibility;
text-shadow: rgba(0, 0, 0, 0.5) 1px 1px 2px;
text-transform: uppercase;
text-orientation: sideways-right;
text-combine-upright: none;
direction: ltr;
unicode-bidi: bidi-override;
vertical-align: baseline;

/* Списки */
list-style: circle outside url("images/marker.gif");
list-style-type: circle;
list-style-position: outside;
list-style-image: url("images/marker.gif");

/* Таблицы */
border-collapse: collapse;
border-spacing: 7px 11px;
caption-side: top;
empty-cells: show;
table-layout: fixed;

/* Колонки */
columns: 2 70ex;
column-count: 2;
column-width: 70ex;
column-gap: 1em;
column-rule: thin solid #000;
column-rule-width: thin;
column-rule-style: solid;
column-rule-color: #000;
column-span: all;
column-fill: balance;

/* Печать и страница */
marks: crop cross;
bleed: 6pt;
orphans: 3;
widows: 3;
page-break-after: avoid;
page-break-before: always;
page-break-inside: auto;
break-after: avoid-page;
break-before: page;
break-inside: auto;

/* Настройки контента */
appearance: button;
scroll-behavior: smooth;
resize: vertical;
cursor: pointer;
user-select: none;
pointer-events: none;
touch-action: pan-x;
ime-mode: disabled;
image-rendering: crisp-edges;
image-resolution: 300dpi;
image-orientation: from-image;
object-fit: cover;
object-position: left top;
counter-reset: counter-name;
counter-increment: counter-name;
content: "Section " counter(counter-name) ": ";
quotes: "\00ab" "\00bb";
filter: grayscale(50%);
mix-blend-mode: normal;

/* Цвета, фоны */
color: #000;
opacity: .8;
background: url("images/bg.png") left top no-repeat scroll #fff;
background-image: url("images/bg.png");
background-position: left top;
background-size: 50% 50%;
background-repeat: no-repeat;
background-attachment: scroll;
background-origin: content-box;
background-clip: padding-box;
background-color: #fff;
background-blend-mode: normal;

/* Границы */
border: 1px solid #000;
border-width: 1px;
border-style: solid;
border-color: #000;
border-top: thick double #000;
border-top-width: thick;
border-top-style: double;
border-top-color: #000;
border-right: thin dotted #000;
border-right-…;
border-bottom: thin dashed #000;
border-bottom-…;
border-left: medium groove #000;
border-left-…;
border-radius: 4px 3px 6px / 2px 4px;
border-top-left-radius: 4px 2px;
border-top-right-radius: 3px 4px;
border-bottom-right-radius: 6px 2px;
border-bottom-left-radius: 3px 4px;
border-image: url("images/border.png") 27 27 27 27 round round;
border-image-source: url("images/border.png");
border-image-slice: 27 27 27 27;
border-image-width: 10px;
border-image-outset: 5px;
border-image-repeat: round round;
outline: 1px solid #f00;
outline-width: 1px;
outline-style: solid;
outline-color: #f00;
outline-offset: 10px;
box-shadow: inset 5px 5px 4px 2px rgba(0, 0, 0, 0.5);

/* Преобразования */
transform: rotate(45deg);
transform-origin: center top;
transform-style: preserve-3d;
perspective: 500px;
perspective-origin: center top;
backface-visibility: hidden;

/* Переходы */
transition: opacity 2s ease 0.5s;
transition-property: opacity;
transition-duration: 2s;
transition-timing-function: ease;
transition-delay: 0.5s;

/* Анимация */
animation: mymove 5s linear 2s infinite alternate forwards paused;
animation-name: mymove;
animation-duration: 5s;
animation-timing-function: linear;
animation-delay: 2s;
animation-iteration-count: infinite;
animation-direction: alternate;
animation-fill-mode: forwards;
animation-play-state: paused;
will-change: auto;
```
