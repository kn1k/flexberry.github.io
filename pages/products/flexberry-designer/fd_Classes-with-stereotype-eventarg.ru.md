---
title: События и параметры событий (классы со стереотипом eventarg)
sidebar: flexberry-designer_sidebar
keywords: Flexberry Designer, Flexberry ORM, Public
toc: true
permalink: ru/fd_classes-with-stereotype-eventarg.html
folder: products/flexberry-designer/
lang: ru
---

# Описание события и что и как с него генерируется
`Flexberry` позволяет пользователю описывать события и их аргументы, для возможной последующей генерации в исходный код на CLR-совместимом языке, в частности, `C#`.


События описываются внутри UML-классов, в секции методов, в следующем виде:
```
 /[AccessModifier]Name([ParamName:TypeEventArgs)
```
Обратите внимание, что параметр должен быть один и его тип был UML-классом со стереотипом eventarg, если это не так, в процессе генерации произойдёт ошибка.


Пример описания аргументов события и самого события:
![](/images/pages/img/Flexberry plugins/eventeventargs.gif)
## Генерация класса аргументов события
Класс наследующийся от `System.EventArgs.` Также генерируется определение делегата.


Пример для нашей диаграммы:
```
   // *** Start programmer edit section *** (Аргументы CustomAttributes)
    // *** End programmer edit section *** (Аргументы CustomAttributes)
    public class Аргументы : System.EventArgs
    {        
        private string fарг1;
        // *** Start programmer edit section *** (Аргументы CustomMembers)
        
        // *** End programmer edit section *** (Аргументы CustomMembers)
        // *** Start programmer edit section *** (Аргументы.арг1 CustomAttributes)
        // *** End programmer edit section *** (Аргументы.арг1 CustomAttributes)
        public virtual string арг1
        {
            get
            {
                // *** Start programmer edit section *** (Аргументы.арг1 Get start)
                // *** End programmer edit section *** (Аргументы.арг1 Get start)
                string result = this.fарг1;
                // *** Start programmer edit section *** (Аргументы.арг1 Get end)
                // *** End programmer edit section *** (Аргументы.арг1 Get end)
                return result;
            }
            set
            {
                // *** Start programmer edit section *** (Аргументы.арг1 Set start)
                // *** End programmer edit section *** (Аргументы.арг1 Set start)
                this.fарг1 = value;
                // *** Start programmer edit section *** (Аргументы.арг1 Set end)
                // *** End programmer edit section *** (Аргументы.арг1 Set end)
            }
        }
    }
    public delegate void АргументыHandler(object sender, ICSSoft.Product.Аргументы e);
```
## Что генерируется в классе, где определено событие
В исходный код класса генерируется событие, объявленное типом делегата, а также метод, взводящий это событие.


Пример для нашей диаграммы:
```
  
 public event ICSSoft.Product.АргументыHandler Событие;
        
        // *** Start programmer edit section *** (OnСобытие CustomAttributes)
        // *** End programmer edit section *** (OnСобытие CustomAttributes)
        private void OnСобытие(ICSSoft.Product.Аргументы ea)
        {
            if ((this.Событие != null))
            {
                this.Событие(this, ea);
            }
        }
```
# Свойства аргументов события
## Основные
![](/images/pages/img/Flexberry plugins/argpropsclass.jpg)
{| border="2"
! Свойство-Описание
! Генерация в .Net-язык
|-
| `Name` - имя UML-класса
| Имя `.Net`-класса
|-
| `Description` - некоторое описание класса.
| `DocComment` перед определением класса
|-
| `GenerateCatcher`
| Если установлено, генерируется класс-перехватчик события для использования событийно-ориентированным интерпретатором сценариев (EBSI). Если Вы не планируете использовать EBSI, не устанавливайте эту галочку.
|-
| `Packet, NamespacePostfix` - позволяют настроить сборку и пространство имен, в которое должен генерироваться тип 
| см. [Расположение сборок после генерации кода](location-assembly-after-code-generation.html).
|-
| `PBMembers` - позволяет указать, необходима ли скобка программиста внутри класса для "ручного" внесения членов класса
| Если галочка указана - генерируется скобка программиста для "ручного" внесения членов класса.
|}


## Свойства атрибутов аргументов события
![](/images/pages/img/Flexberry plugins/argpropsattrs.jpg)
{| border="2"
! Свойство-Описание
! Генерация в .Net-язык
|-
| "AccessModifier" - модификатор сгенерированного в .Net-язык свойства
| соответствующий модификатор свойства (# - protected, + - public, - - private)
|-
| "Name", "Type"- очевидно 
|Виртуальное свойство с тем же именем и приватный член класса для этого свойства.

Тип свойства и приватного члена - тип атрибута, преобразованный от исходного согласно [карте отображения типов](classes-with-stereotype--typedef.html).
|-
| "DefaultValue" - значение по-умолчанию.
| Приватному члену прописывается инициализатор с указанным значением по-умолчанию

Если указано значение перечислимого типа, то генерируется инициализация значением этого типа.

Если тип не перечислимый, то берётся соответствующий .Net-тип и проверяется, есть ли публичное статическое свойство с имением "DefaultValue".

Далее, если тип простой стандартный (из namespace System), генерируется простая инициализация константой (напр: int idx=0).

В противном случае генерация останавливается с ошибкой
|-
| `Description`
| `DocComment` перед определением свойства
|-
| `PBCustomAttributes` - скобка программиста
| Если галочка указана - генерируется скобка программиста для "ручного" внесения .Net атрибутов перед кодом свойства.
|-
| `PBGetEnd` - скобка программиста
| Если галочка указана - генерируется скобка программиста для "ручного" внесения кода перед концом аксессора `get`.
|-
| `PBGetStart` - скобка программиста
| Если галочка указана - генерируется скобка программиста для "ручного" внесения кода после начала аксессора get.
|-
| `PBSetEnd` - скобка программиста
| Если галочка указана - генерируется скобка программиста для "ручного" внесения кода перед концом аксессора set.
|-
| `PBSetStart` - скобка программиста
| Если галочка указана - генерируется скобка программиста для "ручного" внесения кода после начала аксессора set.
|}

## Свойства методов аргументов события
Свойства и генерация методов, см. [здесь](class-methods-and-method-parameters.html).
# Свойства события
![](/images/pages/img/Flexberry plugins/eventprops.jpg)
{| border="2"
! Свойство-Описание
! Генерация в .Net-язык
|-
| `AccessModifier` - модификатор события
| Соответствующий модификатор в определении события (# - protected, + - public, - - private)
|-
| `Name` - имя события
| Имя события
|-
| `Description` - описание
| `DocComment` перед определением метода OnСобытие
|-
| `Type`
| Не учитывается
|-
| `IsEvent` - указывает, что это - событие, а не метод, дублирует "/" в определении события.
| Генерируется событие, а не метод.
|-
| `PBCustomAttributes`
| Если флажок выставлен, - генерируется скобка программиста перед определением метода OnСобытие
|}