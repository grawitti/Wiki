## Стандартная библиотека std

### static_cast - явное приведение типов

**static_cast** - приводит значение одного типа в значение другого типа.

**Синтаксис:**
```c++
static_cast<A>(b) // приводит значение b к типу А
```
Пример:

```c++
int i = 1;
double d = static_cast<double>(i); // d = 1.0
```
---

### reinterpred_cast

**reinterpred_cast** - реитерпретирует данные (байты в памяти).

**Синтаксис:**
```c++
reinterpred_cast<A>(b) // реитерпретирует байты памяти со значением переменной b в тип A
```

Пример:
```c++
char ch = '0';
int i = reinterpred_cast<int>(ch); // возможен неожиданный результат
```
---
### const_cast

**const_cast** - аннулирует квалификатор `const`.

**Синтаксис:**
```c++
const T* a = 0; // создаем указатель а на объект класса Т со значением 0
T* b = const_cast<T*>(a); // присваиваем указателю b адрес указателя а
*b = 1; // изменяем значение, теперь *a = 1
```

Пример:
```c++
const int* i = new int{0};
int* x = const_cast<int>(i);
*x = 1; // *i = 1
```

>**Примечание:** Если логика программы требует использования приведения типов, значит необходимо изменить логику так, чтобы обойтись без этого ужастного и непредсказуемого действия.
---