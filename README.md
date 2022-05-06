# Вопросы к экзамену по ООП

## 1. Что такое объект?

**Объект** представляет собой опознаваемый предмет, единицу или сущность (реальную или абстрактную), имеющую четко определенное функциональное назначение в предметной области. Для определения объектов предметной области требуется рассмотреть понятия, которыми оперируют специалисты автоматизируемой предметной области..

**Объект** - то, что может быть индивидуально описано и рассмотрено.

## 2. Определение системы и три примера систем.

**Система** - множество взаимосвязанных и взаимодействующих объектов для решения одной или множества задач (достижения одной или множества целей).

Примеры систем:

- Солнечная систем.
- растение.
- живой организм.
- автомобиль.
- компьютер.
- разговорный язык.
- математический язык.
- нотные записи.
- футбольный клуб,

## 3. Жизненный цикл объекта.

![untitled](/assets/screenshot_1.png)

## 4. Взаимодействие объектов. Три примера взаимодействия объектов.

При использовании технологи ООП решение задачи представляется в виде результата **взаимодействия** отдельных функциональных элементов (объектов/экземпляров) некоторой системы, происходящие в предметной области поставленной задачи.

В такой системе, каждый входящий функциональный элемент, получив некоторое входное воздействие (сообщение), выполняет заранее определенное действие.

Например, он может:

- опустить монету в автомат по продаже газет;
- нарисовать круг или квадрат;
- вычислить их площадь или периметр;
  
т.е. он воздействует на себя или на другой объект, изменяя состояние себя или другого элемента. Передавая сообщения, от элемента к элементу, система выполняет определенные действия.

![untitled](/assets/screenshot_2.png)

## 5. Класс. Назначение и синтаксис описания.

**Класс** – множество объектов, имеющих общую структуру и поведение. Объекты, не связанные общностью структуры и поведения, нельзя объединять в класс. «Класс – это контракт между клиентами и абстракцией». Любой объект называют так же экземпляром класса.

- Описание заголовочной части класса
  
```cpp
class MyClass {
private:
//список скрытых элементов класса
public:
MyСlass(); // конструктор
//список доступных элементов класса
~MyClass(); //деструктор
protected:
//список защищенных элементов класса
}; 
```

- Описание части реализации класса

```cpp
void MyClass::foo() {
    // тело метода (код алгоритма метода) 
}
```

## 6. Жизненный цикл виртуального объекта и его реализация на языке С++

Виртуальные функции определяются в базовом классе с ключевым 
словом virtual и они переопределяются (замещаются в производных классах). При этом прототипы функций в разных классах идентичны, но функции отличаются алгоритмами.

Три правила полиморфизма, начинают работать правильно, связывают объект и метод на этапе выполнения правильно:

- При использовании указателя на базовый класс, которому присвоен адрес объекта производного класса, вызовет метод присвоенного объекта.

- Такой же результат будет и у внешней функции, параметр которой указатель на базовый класс, а примет она в качестве параметра адрес производного класса.

- Виртуальная функция остается таковой во всех производных классах. Если она в каком-то классе не переопределена, то механизм виртуальных функций в этом классе сохраняется. Виртуальная функция может быть дружественной другому классу. При реализации виртуальной функции наследниками слово virtual не указывается.

## 7. Архитектура системы. Иерархия объектов

Архитектура системы так или иначе строится путем создания иерархии объектов и взаимодействия между объектами.

Наследование поддерживает иерархические отношения между классами – is a. Основой выявления таких отношений, является исследование задачи, проведение классификации выявленных сущностей – классов, определения их общих свойств и поведения. На верхний уровень иерархии выносятся свойства и операции общие для всех сущностей, далее уровни выстраиваются по такому же принципу.

![untitled](/assets/screenshot_3.png)

## 8. Программа – система.

Любая программа (приложение), написанная с использованием ООП является системой.
Приведем пример схемы приложения:

![untitled](/assets/screenshot_4.png)

## 9. Наследование. Реализация наследования на языке С++.

Наследование - возможность создания производных классов (классов наследников), взяв за основу методы и элементы базового класса (класса родителя).

Язык С++ поддерживает реализацию двух видов наследования:

- Простое, новый класс формируется на основе одного существующего класса
- Множественное, создание нового класса на основе нескольких существующих классов

```cpp
class ChildClass : public /* private | protected */  ParentClass {
    // тело класса
};
```

## 10. Управление доступом при наследовании

- `private`. Члены класса, объявленные как private могут использоваться только функциями-членами и друзьями (классами или функциями) класса.
- `protected`. Члены класса, объявленные как protected могут использоваться функциями-членами и друзьями (классами или функциями) класса. Кроме того, они могут использоваться производными классами данного класса.
- `public`. Члены класса, объявленные как public могут использоваться любой функцией.

## 11. Инкапсуляция

Инкапсуляция – объединение всех свойств объекта, определяющих его состояние и поведение в единую абстракцию и ограничение доступа к реализации. Суть инкапсуляции - доступ к данным разрешен только методам класса.

Для обеспечения скрытия данных и поддержки инкапсуляции в классах С++ используются уровни доступа к членам класса:

- `private` - список полей и методов объявленных после спецификатора private
будет доступен только методам этого класса и друзьям.
- `public` - члены класса доступные другим функциям и объектам программы
Методы этой части класса представляют интерфейс класса.
- `protected` – члены класса доступные в классе, наследникам, друзьям.

## 12. Полиморфизм

Полиморфизм – переопределение наследниками методов выполняющих одну задачу, но по разному для разных классов иерархии.

Полиморфизм позволяет строить более гибкие и совершенные иерархии классов, заменяя в производных классах методы в соответствии с требованиями разрабатываемой программы.

## 13. Управление доступом к элементам класса

- `private`:
  - Всегда недоступен с любым доступом к производным данным;

- `protected`:
  - `private` в производном классе при использовании `private` наследования.
  - `protected` в производном классе при использовании `protected` наследования.
  - `protected` в производном классе при использовании `public` наследования.

- `public`:
  - `private` в производном классе при использовании `private` наследования;
  - `protected` в производном классе при использовании `protected` наследования;
  - `public` в производном классе при использовании `public` наследования;

## 14. Конструктор и деструктор объекта

**Конструктор** класса - это метод, обеспечивающие создание(инициализацию полей) экземпляров класса (объектов). Объект это переменная класса.

В классе С++ может быть несколько конструкторов, т.к. для них допускается перегрузка.

Виды конструкторов: 

- Конструктор по умолчанию. Если программист не включил в класс ни одного конструктора, то компилятор создаст его автоматически, и он будет вызывается автоматически при определении объекта.
- Явно определенный конструктор. Такой конструктор реализуется по формату функции, его имя – это имя класса.
  - Без параметров – его называют конструктором по умолчанию.

Также существуют определенный конструктор с параметрами, а также конструктор копирования. Они описаны в билетах ниже.
  
```cpp
class MyClass {
public:
  MyClass(); // конструктор
};
```

**Деструктор** - метод, обеспечивающий правильное удаление объектов.

Виды деструкторов:

- Деструктор по умолчанию. Вызывается автоматически, когда объект выходит из области видимости. Видимость объектов определяется по правилам видимости локальных, глобальных, статических переменных.
- Явно определенный деструктор. Требуется, если среди членов данных имеются динамические переменные, которые удаляются другими средствами.

```cpp
class MyClass {
public:
  ~MyClass(); // деструктор
};
```

## 15. Параметризированные конструкторы

Параметризированный конструктор создает объект и инициализирует члены данных значениями параметров. В классе может быть несколько перегруженных конструкторов с различным количеством параметров. Параметры могут быть любого типа, кроме типа этого класса.

```cpp
class MyClass {
public:
  MyClass(int field); // конструктор c параметром
};
```

## 16. Конструктор копирования

Стандартный конструктор копирования, который осуществляет поэлементное копирование однотипных объектов. Вызывается при присваивании объектов одного типа.

Не стандартный конструктор копирования (создается программистом) включается в класс, в котором есть динамически создаваемые члены данных.

Такой конструктор имеет один параметр – ссылку на объект своего класса.

```cpp
class MyClass {
  int a;
public:
  MyClass(int a); // конструктор копирования
};

MyClass::MyClass(int a) {
  this->a = a;
}
```

## 17. Объявление объекта и доступ к его элементам

Чтобы объявить объект, необходимо указать класс/тип объекта, а затем имя объекта.

Чтобы использовать свойства и методы объекта, необходимо использовать `.` после его имени.

```cpp
class MyClass {
public:
  void foo();
};

int main() {
  MyClass obj; // объявление объекта
  obj.foo(); // вызов метода объекта
}
```

## 18. Указатели и ссылки на объект

Чтобы использовать свойства и методы через указатель на объект, необходимо использовать `->` вместо `.`

```cpp
class MyClass {
public:
  void foo();
};

int main() {
  MyClass obj;
  MyClass obj_ptr = &obj;
  obj_ptr->foo();
}
```

## 19. Указатель this

При вызове функции-члена ей неявно передается указатель на вызывающий объект — указатель `this`.

`this` полезен при перегрузке операторов, а также в ситуациях, когда функция-член должна использовать указатель на вызывающий объект.

```cpp
class ChildClass {
ParentClass* parent_ptr;
std::vector <ParentClass*> child_vector;
public:
  
};

MyClass::MyClass(ParentClass* parent_ptr) {
  parent_ptr->child_vector.push_back(this);
}
```

## 20 Присвоение объектов

Если тип двух объектов одинаков, то один объект можно присвоить другому. По умолчанию, когда один объект присваивается другому, делается побитовая копия всех атрибутов копируемого объекта.

Стандартное присваивание можно переопределить, перегрузив оператор присваивания для конкретного класса.

## 21. Объекты в качестве возвращаемого значения функции

Когда функция возвращает объект, автоматически создается временный объект, содержащий возвращаемое значение. Именно этот объект фактически возвращается функцией. После того, как значение возвращено, этот объект уничтожается.

Уничтожение временного объекта может вызывать неожиданные побочные эффекты в некоторых ситуациях. Например, если возвращае­мый функцией объект имеет деструктор, освобождающий динамически зарезервированную па­мять. Для решения этой проблемы используется перегрузка оператора присваивания и определение конструктора копирования.

## 22. Встраиваемая функция

В ООП при разработке классов создается много маленьких функций, это порождает много вызовов, что затратно по времени. В С++ преодолеть эту трудность помогают функции - подстановки (inline).

Такие функции можно определить в классе, а можно объявить в классе как обычную функцию – член, а реализовать вне класса как функцию inline.

Тела функций встраиваются в код на месте вызова этой функции при выполнении препроцессорной обработки

```cpp
inline void foo() {
  // тело функции
}
```

## 23. Дружественная функция

Дружественная по отношению к классу функция имеет доступ к приватным и защищённым полям и методам класса при помощи ключевого слова `friend`.

Обычно дружественные функции используются для перегрузки операторов или имеют вспомогательное назначение — например, вывод.

```cpp
friend void foo();
```

## 24. Дружественный класс

Класс можно объявить дружественным по отношению к другому классу при ключевого слова `friend`. В таком случае в классе можно будет получить доступ к приватным и защищённым свойствам и методам другого класса.

```cpp
class MyClass1 {
friend class MyClass2;
}
```

## 25. Операторы new и delete

Операция `new` предназначена для создания объекта.

Время жизни объекта, созданного с помощью `new` , не ограничивается областью видимости, в которой он был создан.

```cpp
MyClass* obj = new MyClass;
}
```

Операция `delete` уничтожает объект, созданный с помощью `new`.

```cpp
delete obj;
```

## 26. Защищенные члены класса

Если необходимо защитить член класса от доступа извне, но позволить использовать его производным классам, используется другое ключевое слово — protected (защищенный). Если продолжить аналогию, это напоминает семейную ценность, передаваемую по наследству.

Защищен­ный член подобен частному, за исключением механизма наследования. При наследовании защищенного члена производный класс также имеет к нему доступ. Таким образом, указав специфи­катор доступа protected, можно позволить использовать атрибуты и методы внутри иерархии и запретить доступ к нему извне этой иерархии.

```cpp
class MyClass {
protected:
  //защищенные члены класса
};
```

## 27. Множественное наследование

Множественное наследование - это создание нового класса на основе нескольких существующих классов.

```cpp
class ParentClass1 {
  // тело класса
};

class ParentClass2 {
  // тело класса
};

class ChildClass: public /* protected | private*/ ParentClass1, public /* protected | private*/  ParentClass2 {
  // тело класса
};
```

## 28. Виртуальные базовые классы

При множественном наследовании может возникнуть неоднозначность.

В качестве примера, рассмотрим следующую задачу. Класс ChildClass является наследником классов ParentClass1 и ParentClass2.

```cpp
class BaseClass {
public:
  int num;
};

class ParentClass1 : public BaseClass{
  
};

class ParentClass2 : public BaseClass{
  
};

class ChildClass : public ParentClass1, public  ParentClass2 {
};

int main() {
   ChildClass obj;
   obj.num = 1;
   // Ошибка! неявное имя переменной
   return 0;
}
```

Программу можно исправить двумя способами:

1. Применить оператор разрешения области видимости `::` к переменной num

```cpp
class BaseClass {
public:
  int num;
};

class ParentClass1 : public BaseClass{
  
};

class ParentClass2 : public BaseClass{
  
};

class ChildClass : public ParentClass1, public  ParentClass2 {
};

int main() {
   ChildClass obj;
   obj.ParentClass1::num = 1;
   return 0;
}
```

Оператор разрешения области видимости `::` позволяет явно выбрать вариант производного класса. Однако данный способ решения порождает проблемы: Что если на самом деле нужна лишь одна копия объекта, можно ли предот­вратить дублирование объектов?

1. Использование виртуальных базовых классов

```cpp
class BaseClass {
public:
  int num;
};

class ParentClass1 : virtual public BaseClass {
  
};

class ParentClass2 : virtual public BaseClass {
  
};

class ChildClass : public ParentClass1, public  ParentClass2 {
};

int main() {
   ChildClass obj;
   obj.num = 1;
   return 0;
}
```

Как видим, перед именем базового класса в спецификации производного класса стоит ключевое слово `virtual`.

Теперь оба класса являются наследниками виртуального базового класса `BaseClass`, и любые их наследники будут со­ держать лишь одну его копию. Следовательно, выражение `obj.num = 1` становится однозначным

## 29. Указатель на объект производного класса

Если класс `MyClass1` является производным от класса `MyClass2`, то указатель типа `MyClass1*` может ссылаться на объекты типа `MyClass2`, если его привести к типу указателя `MyClass2`.

```cpp
MyClass1* obj_ptr;
MyClass1 obj;
obj_ptr = &obj;
((MyClass2*)obj_ptr)->foo();
```

## 30. Виртуальные методы. Наследование виртуальных методов

Виртуальная функция — функция-член, объявленная в базовом классе и переопределенная в производном.

Чтобы создать виртуальную функ­цию, следует указать ключевое слово `virtual` перед ее объявлением в базовом классе.

По существу, виртуальная функция реализует принцип “один интер­фейс, несколько методов”, лежащий в основе полиморфизма.

При наследовании виртуальной функции ее виртуальная природа также наследует­ся.

Виртуальные функции являются иерархическими.

Виртуальную функцию не обязательно определять в классе наследнике. В этом случае вызывается функция, определенная в базовом классе.

## 31.	Чисто виртуальные функции и абстрактные классы.
## 32.	Перегрузка функций.
## 33.	Перегрузка унарных операторов.
## 34.	Перегрузка бинарных операторов.
## 35.	Перегрузка оператора индексации массивов [ ]
## 36.	Аргументы, передаваемые функции по умолчанию.
## 37.	Определение адреса перегруженной функции.
## 38.	Класс vector.
## 39.	Класс string.
## 40.	Класс map и multimap.
## 41.	Объявление элементов класса спецификацией static.
## 42.	Объявление элементов класса спецификацией const.
## 43.	Шаблон функции.
## 44.	Шаблон класса.
## 45.	Контейнеры и итераторы.
## 46.	Контейнер – динамический массив.
## 47.	Контейнер – ассоциативный список.
## 48.	Исключительные ситуации.
## 49.	Приведение типов.
## 50.	Сигналы и обработчики.
## 51.	Ввод-вывод в С++. Потоки.
## 52.	Форматированный ввод-вывод данных.
