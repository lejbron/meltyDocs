Температурные настройки
=======================

Термистор стола
---------------

Зависит от *термистора стола*.

.. code-block:: c++

  #define TEMP_SENSOR_BED 1

Ограничения минимальной температуры
-----------------------------------

.. code-block:: c++

  #define HEATER_0_MINTEMP   5
  #define HEATER_1_MINTEMP   5
  #define HEATER_2_MINTEMP   5
  #define HEATER_3_MINTEMP   5
  #define HEATER_4_MINTEMP   5
  #define HEATER_5_MINTEMP   5
  #define BED_MINTEMP        5


Ограничения максимальной температуры
------------------------------------

.. code-block:: c++

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

.. code-block:: c++

  #define DEFAULT_Kp 21.68
  #define DEFAULT_Ki 2.00
  #define DEFAULT_Kd 58.61

Защита нагрева сопла
--------------------

https://marlinfw.org/docs/gcode/M302.html

.. code-block:: c++

  #define PREVENT_COLD_EXTRUSION
  #define EXTRUDE_MINTEMP 170
