[![](https://iarduino.ru/img/logo.svg)](https://iarduino.ru)[![](https://wiki.iarduino.ru/img/git-shop.svg?3)](https://iarduino.ru) [![](https://wiki.iarduino.ru/img/git-wiki.svg?2)](https://wiki.iarduino.ru) [![](https://wiki.iarduino.ru/img/git-lesson.svg?2)](https://lesson.iarduino.ru)[![](https://wiki.iarduino.ru/img/git-forum.svg?2)](http://forum.trema.ru)

# iarduino\_IR

**This is a library for Arduino IDE. It allows to work with [IR-reciever](https://iarduino.ru/shop/Sensory-Datchiki/ik-priemnik-trema-modul.html) and [IR-transmitter](https://iarduino.ru/shop/Expansion-payments/ik-peredatchik-trema-modul.html) modules made by iArduino.ru**

**Данная библиотека для Arduino IDE позволяет работать с модулями [ИК-приёмник](https://iarduino.ru/shop/Sensory-Datchiki/ik-priemnik-trema-modul.html) и [ИК-передатчик](https://iarduino.ru/shop/Expansion-payments/ik-peredatchik-trema-modul.html) от [iArduino.ru](https://iarduino.ru)**

> Подробнее про установку библиотеки читайте в нашей [инструкции](https://wiki.iarduino.ru/page/Installing_libraries/).

> Подробнее про подключение к [Arduino UNO](https://iarduino.ru/shop/boards/arduino-uno-r3.html)/[Piranha UNO](https://iarduino.ru/shop/boards/piranha-uno-r3.html) читайте на нашей wiki: [ИК-приёмник](https://wiki.iarduino.ru/page/ik-priemnik/), [ИК-передатчик](https://wiki.iarduino.ru/page/ik-peredatchik/)


| Модель | Ссылка на магазин |
|---|---|
| <p>ИК-приёмник</p> <img src="https://wiki.iarduino.ru/img/resources/620/620.svg" width="100px"></img>| https://iarduino.ru/shop/Sensory-Datchiki/ik-priemnik-trema-modul.html |
| <p>ИК-передатчик</p> <img src="https://wiki.iarduino.ru/img/resources/758/758.svg" width="100px"></img>| https://iarduino.ru/shop/Expansion-payments/ik-peredatchik-trema-modul.html |


Библиотека использует второй аппаратный таймер, как для раскодирования данных с ИК-приёмника «в фоновом режиме», так и для формирования несущей частоты ИК-передатчика. Не выводите сигнал ШИМ на 3 или 11 вывод, это помешает корректной работе библиотеки.


## Назначение функций:

**Подробное описание работы с библиотекой и примеры смотрите на нашем сайте: [ИК-приёмник](https://wiki.iarduino.ru/page/ik-priemnik/), [ИК-передатчик](https://wiki.iarduino.ru/page/ik-peredatchik/)**

### Управление ИК-приёмником:

**Подключаем библиотеку**

```C++
#include <iarduino_IR_RX.h> // Подключаем библиотеку.
iarduino_IR_RX ОБЪЕКТ ( №_ВЫВОДА [, ИНВЕРСИЯ ] ); // Объявляем объект.
```

**Инициализация работы** 

```C++
ОБЪЕКТ.begin(); // Инициализация работы с ИК-приёмником.
```

**Проверка наличия данных** 

```C++
ОБЪЕКТ.check( [ УДЕРЖАНИЕ ] ); // Проверка наличия принятых с пульта данных.
```

**Работа с протоколом** 

```C++
ОБЪЕКТ.protocol( [ ПАРАМЕТР ] ); // Получение, установка или сброс протокола передачи данных.
```

**Возвращает код** 

```C++
Переменная ОБЪЕКТ.data; // Возвращает код кнопки, принятый с пульта.
```

**Размер принятого кода** 

```C++
Переменная ОБЪЕКТ.length; // Возвращает размер принятого кода, в битах.
```

**Возвращает флаг**

```C++
ОБЪЕКТ.key_press; // Возвращает флаг, указывающий на то, что кнопка нажимается а не удерживается.
```

### Управление ИК-передатчиком:

```C++
#include <iarduino_IR_TX.h> // Подключаем библиотеку
iarduino_IR_TX ОБЪЕКТ ( №_ВЫВОДА [, ИНВЕРСИЯ ] ); // Объявляем объект.
```

**Инициализация работы** 

```C++
ОБЪЕКТ.begin(); // Инициализация работы с ИК-передатчиком.
```

**Передача данных**

```C++
ОБЪЕКТ.send( ДАННЫЕ [, УДЕРЖАНИЕ ] ); // Передача данных.
```

**Установка протокола** 

```C++
ОБЪЕКТ.protocol( СТРОКА ); // Установка протокола передачи данных.
```

**Установка несущей частоты** 

```C++
ОБЪЕКТ.frequency; // Устанавливает несущую частоту передачи данных в кГц.
```

