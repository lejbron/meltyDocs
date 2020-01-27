
Настройка маханических параметров
=================================

Концевые выключатели
--------------------

Измените согласно коду ниже.

Используемые на плате порты

.. code-block:: c++

  #define USE_XMIN_PLUG
  #define USE_YMAX_PLUG
  #define USE_ZMAX_PLUG

Инвертирование направления

.. code-block:: c++

  #define X_MIN_ENDSTOP_INVERTING true // Set to true to invert the logic of the endstop.
  #define Y_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define X_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Y_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
  #define Z_MIN_PROBE_ENDSTOP_INVERTING false // Set to true to invert the logic of the probe.

Драйверы шаговых моторов
------------------------

Зависит от *использумых драйверов*.

.. code-block:: c++

  #define X_DRIVER_TYPE  A4988
  #define Y_DRIVER_TYPE  A4988
  #define Z_DRIVER_TYPE  A4988
  #define E0_DRIVER_TYPE A4988

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

Ограничение максимальной скорости перемещения
---------------------------------------------

.. code-block:: c++

  #define DEFAULT_MAX_FEEDRATE          {300, 300, 5, 25}    // (mm/sec)


Ускорение перемещения по осям
-----------------------------

.. code-block:: c++

  #define DEFAULT_MAX_ACCELERATION      { 2000, 2000, 100, 10000 }

  #define DEFAULT_ACCELERATION          2000    // X, Y, Z and E acceleration for printing moves
  #define DEFAULT_RETRACT_ACCELERATION  2000    // E acceleration for retracts
  #define DEFAULT_TRAVEL_ACCELERATION   2000    // X, Y, Z acceleration for travel (non printing) moves

Изменение направления вращения моторов
--------------------------------------

При необходимости изменить напрвление мотора используйте следующие константы:

.. code-block:: c++

  #define INVERT_X_DIR false
  #define INVERT_Y_DIR true
  #define INVERT_Z_DIR false

  #define INVERT_E0_DIR false

Homing
------

.. code-block:: c++

  #define X_HOME_DIR -1
  #define Y_HOME_DIR 1
  #define Z_HOME_DIR 1

Указание размера области печати
-------------------------------

.. code-block:: c++

  #define X_BED_SIZE 190
  #define Y_BED_SIZE 190

  #define X_MIN_POS 0
  #define Y_MIN_POS 0
  #define Z_MIN_POS 0
  #define X_MAX_POS X_BED_SIZE
  #define Y_MAX_POS Y_BED_SIZE
  #define Z_MAX_POS 200

Отступ по оси Z
---------------

.. code-block:: c++

  #define HOTEND_OFFSET_Z { 0.0, 1.3 }


Automatic Bed Leveling
----------------------

1. #define PROBE_MANUALLY (878)
2. #define MESH_BED_LEVELING (1209)
3. #define LCD_BED_LEVELING (1332)

.. code-block:: c++

  #if ENABLED(LCD_BED_LEVELING)
    #define MESH_EDIT_Z_STEP  0.025 // (mm) Step size while manually probing Z axis.
    #define LCD_PROBE_Z_RANGE 4     // (mm) Z Range centered on Z_MIN_POS for LCD Z adjustment
    //#define MESH_EDIT_MENU        // Add a menu to edit mesh points
  #endif
