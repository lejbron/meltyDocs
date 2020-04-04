
Настройка маханических параметров
=================================

Концевые выключатели
--------------------

В этом разделе необходимо задать используемые на плате порты:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 569
   :end-line: 579

При необходимости инвертировать конецевые выключатели измените следующие
константы:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 605
   :end-line: 614

Драйверы шаговых моторов
------------------------

Необходимо непорседственно указать модель используемых дравйров шаговых
двигателей :term:`A4988`.
MARLIN_R2D2

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 614
   :end-line: 643


Настройка перемещения по осям
-----------------------------

Шаги перемещения
~~~~~~~~~~~~~~~~

Оси X и Y
``````````

- Шаговый двигатель: 200 шагов на оборот, 16 микро-шагов на шаг (ПЕРЕМЫЧКИ)
- Приводной ремень GT2: шаг 2мм
- Шкив: 20 зубьев

Сколько шагов должен совершить двигатель, чтобы по оси X и Y было совершено
перемещение ровно в 1 мм:

(200*16)/(2*20) = 80

Ось Z
``````

- Мотор с интегрированным трапецеидальным винтом:

  - Диаметр 8 мм
  - Шаг 2 мм
  - Заходность 4

  Количество шагов: (200*16)/(2*4) = 400

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 681
   :end-line: 688

Ограничение максимальной скорости перемещения
---------------------------------------------

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 688
   :end-line: 695

Ускорение перемещения по осям
-----------------------------

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 695
   :end-line: 703

Изменение направления вращения моторов
--------------------------------------

При необходимости изменить напрвление моторов измените следующие константы:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 945
   :end-line: 950

Homing
------

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 969
   :end-line: 975

Указание размера области печати
-------------------------------

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 977
   :end-line: 989

Отступ по оси Z
---------------

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 279
   :end-line: 286

Automatic Bed Leveling
----------------------

1. Первый шаг:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 790
   :end-line: 796

2. Второй шаг:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 1050
   :end-line: 1094

3. Третий шаг:

.. include:: MARLIN_R2D2\Configuration.h
   :code: C++
   :start-line: 1210
   :end-line: 1222
