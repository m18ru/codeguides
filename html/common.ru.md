# Оформление HTML

* Должен быть корректным документом HTML5.
* Должен быть XML‐совместимым (даёт более однозначную разметку, позволяет работать с кодом инструментами XML):
  * Не допустим пропуск корневых тегов, должна быть полная структура (`html`, `head`, `body`).
  * Закрывающие теги всегда должны быть.
  * Непарные теги должны закрываться (`<br />`).
  * Теги и атрибуты должны быть в нижнем регистре.
  * Значение атрибутов должно быть написано в кавычках.
* Для значений атрибутов должны использоваться двойные кавычки.
* Должна использоваться правильная семантика документа с использованием структурных тегов HTML5 (по семантике стоит ориентироваться на [стандарт](https://www.w3.org/TR/html51/)).
* Использование неоправданных структурой обёрток должно быть сведено к минимуму.
* Отступ должен делаться табуляцией, открытие тега создаёт один уровень отступа, перенос атрибутов также создаёт один уровень отступа.
* Для тегов html и body можно не создавать новый уровень, чтобы повысить удобство работы с кодом и его оптимальность. Для body, при этом, нужно дать пустую строку в начале и конце тега, чтобы лучше было видно границы контента.
* Теги, содержащие другие блочные теги, всегда должны открываться, размещая внутренний контент с новой строки с отступом. Встроенные в строку теги, содержащие контент в виде набора тегов, также должны раскрываться. Если контент текстовый, но тег очень длинный (например из‐за атрибутов), то, скорее всего, его тоже лучше раскрыть.
* Указание кодировки должно быть первым тегом внутри `head`.