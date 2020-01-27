Настройка Marlin
----------------

Скорость запсиси
----------------

Зависит от выбранной материнской платы. Для MKS GEN 1.4 = 250000

Материнская плата
-----------------

.. code:: C++

  #ifndef MOTHERBOARD
    #define MOTHERBOARD BOARD_MKS_GEN_13
  #endif


Название принтера
-----------------

Название принтера будет отображаться на дисплее в процессе работы.

.. code:: C++

  #define CUSTOM_MACHINE_NAME "3D Printer"

Экструдер
---------

Количество экструдеров
----------------------

.. code:: C++

  #define EXTRUDERS 1

Диаметр филамента по умолчанию
------------------------------

.. code:: C++

  #define DEFAULT_NOMINAL_FILAMENT_DIA 3.0

Отступ по оси Z
---------------

.. code:: C++

  #define HOTEND_OFFSET_Z { 0.0, 1.3 }

Температура
===========

Термистор стола
---------------

Зависит от *термистора стола*.

.. code:: C++

  #define TEMP_SENSOR_BED 1

Ограничения минимальной температуры
-----------------------------------

.. code:: C++

  #define HEATER_0_MINTEMP   5
  #define HEATER_1_MINTEMP   5
  #define HEATER_2_MINTEMP   5
  #define HEATER_3_MINTEMP   5
  #define HEATER_4_MINTEMP   5
  #define HEATER_5_MINTEMP   5
  #define BED_MINTEMP        5


Ограничения максимальной температуры
====================================

.. code:: C++

  #define HEATER_0_MAXTEMP 275
  #define HEATER_1_MAXTEMP 275
  #define HEATER_2_MAXTEMP 275
  #define HEATER_3_MAXTEMP 275
  #define HEATER_4_MAXTEMP 275
  #define HEATER_5_MAXTEMP 275
  #define BED_MAXTEMP      150


PID settings
------------

Необходимо настраивать в процессе калибровки

.. code:: C++

  #define DEFAULT_Kp 21.68
  #define DEFAULT_Ki 2.00
  #define DEFAULT_Kd 58.61

Защита нагрева сопла
--------------------

https://marlinfw.org/docs/gcode/M302.html

.. code:: C++

  #define PREVENT_COLD_EXTRUSION
  #define EXTRUDE_MINTEMP 170


Концевые выключатели
====================

Измените согласно коду ниже.

Используемые на плате порты

.. code:: C++

  #define USE_XMIN_PLUG
  #define USE_YMAX_PLUG
  #define USE_ZMAX_PLUG

Инвертирование направления

.. code:: C++

  #define X_MIN_ENDSTOP_INVERTING true // Set to true to invert the logic of the endstop.
  #define Y_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define X_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Y_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MIN_PROBE_ENDSTOP_INVERTING false // Set to true to invert the logic of the probe.

Драйверы шаговых моторов
========================

Зависит от *использумых драйверов*.

.. code:: C++

  #define X_DRIVER_TYPE  A4988
  #define Y_DRIVER_TYPE  A4988
  #define Z_DRIVER_TYPE  A4988
  #define E0_DRIVER_TYPE A4988

Настройка перемещения по осям
=============================

Шаги перемещения
----------------

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

Экструдер
``````````

НАСТРОЙКА ЭКСТРУДРЕРА

#define PREVENT_COLD_EXTRUSION
#define EXTRUDE_MINTEMP 170

Ограничение максимальной скорости перемещения
---------------------------------------------

.. code:: C++

  #define DEFAULT_MAX_FEEDRATE          {300, 300, 5, 25}    // (mm/sec)


Ускорение перемещения по осям
-----------------------------

.. code:: C++

  #define DEFAULT_MAX_ACCELERATION      { 2000, 2000, 100, 10000 }

  #define DEFAULT_ACCELERATION          2000    // X, Y, Z and E acceleration for printing moves
  #define DEFAULT_RETRACT_ACCELERATION  2000    // E acceleration for retracts
  #define DEFAULT_TRAVEL_ACCELERATION   2000    // X, Y, Z acceleration for travel (non printing) moves

Изменение направления моторов
=============================

При необходимости изменить напрвление мотора используйте следующие константы:

.. code:: C++

  #define INVERT_X_DIR false
  #define INVERT_Y_DIR true
  #define INVERT_Z_DIR false

  #define INVERT_E0_DIR false

Homing
======

.. code:: C++

  #define X_HOME_DIR -1
  #define Y_HOME_DIR 1
  #define Z_HOME_DIR 1

Указание размера области печати
===============================

.. code:: C++

  #define X_BED_SIZE 190
  #define Y_BED_SIZE 190

  #define X_MIN_POS 0
  #define Y_MIN_POS 0
  #define Z_MIN_POS 0
  #define X_MAX_POS X_BED_SIZE
  #define Y_MAX_POS Y_BED_SIZE
  #define Z_MAX_POS 200

Automatic Bed Leveling
======================

1. #define PROBE_MANUALLY (878)
2. #define MESH_BED_LEVELING (1209)
3. #define LCD_BED_LEVELING (1332)

#if ENABLED(LCD_BED_LEVELING)
  #define MESH_EDIT_Z_STEP  0.025 // (mm) Step size while manually probing Z axis.
  #define LCD_PROBE_Z_RANGE 4     // (mm) Z Range centered on Z_MIN_POS for LCD Z adjustment
  //#define MESH_EDIT_MENU        // Add a menu to edit mesh points
#endif


Настройка EEPROM
================

GLOSSARY

Electrically Erasable Programmable Read-Only Memory

.. code:: C++


  #define EEPROM_CHITCHAT       // Give feedback on EEPROM commands. Disable to save PROGMEM.
  #if ENABLED(EEPROM_SETTINGS)
    //#define EEPROM_AUTO_INIT  // Init EEPROM automatically on any errors.
  #endif

Дисплей
=======

1. #define DISPLAY_CHARSET_HD44780 CYRILLIC
2. #define SDSUPPORT
3. #define LCD_FEEDBACK_FREQUENCY_DURATION_MS 0 //2
   #define LCD_FEEDBACK_FREQUENCY_HZ 0 //5000
4. #define MKS_MINI_12864
