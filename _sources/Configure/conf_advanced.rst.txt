Расширенные настройки Marlin
============================

Изменение этих натсроек не всегда необходимо, но о них полезно помнить.

Thermal Protection
------------------

В некоторых случаях необходимо увеличить периоды ожидания механизмов термальной
защиты.

.. code-block:: c++

  #if ENABLED(THERMAL_PROTECTION_HOTENDS)
    #define THERMAL_PROTECTION_PERIOD 80        // Seconds
    #define THERMAL_PROTECTION_HYSTERESIS 8     // Degrees Celsius

.. code-block:: c++

  #define WATCH_TEMP_PERIOD 40                // Seconds
  #define WATCH_TEMP_INCREASE 4               // Degrees Celsius

.. code-block:: c++

  #if ENABLED(THERMAL_PROTECTION_BED)
    #define THERMAL_PROTECTION_BED_PERIOD 40    // Seconds
    #define THERMAL_PROTECTION_BED_HYSTERESIS 4 // Degrees Celsius

    /**
     * As described above, except for the bed (M140/M190/M303).
     */
    #define WATCH_BED_TEMP_PERIOD 120                // Seconds
    #define WATCH_BED_TEMP_INCREASE 2               // Degrees Celsius
  #endif


Controller Fan
--------------

Extruder coolong Fan
--------------------

.. code-block:: c++

  #define E0_AUTO_FAN_PIN 10

Quick Home
----------

.. code-block:: c++

  #define QUICK_HOME                     // If homing includes X and Y, do a diagonal move initially


Babystepping
------------

.. code-block:: c++

  #define BABYSTEPPING
