Общие настройки
===============

Имя автора
----------

.. code-block:: c++

  #define STRING_CONFIG_H_AUTHOR "lejbron" // Who made the changes.

Скорость запсиси
----------------

Зависит от выбранной материнской платы. Для :term:`MKS GEN` = 250000.

.. code-block:: c++

  #define BAUDRATE 250000

Материнская плата
-----------------

.. code-block:: c++

  #ifndef MOTHERBOARD
    #define MOTHERBOARD BOARD_MKS_GEN_13
  #endif

Название принтера
-----------------

.. code-block:: c++

  #define CUSTOM_MACHINE_NAME "Melty"

Настройка EEPROM
----------------

Подробное описание включения :term:`EEPROM`.

Дисплей
-------

Для указания используемого дисплея (:term:`MKS MINI`) необходимо изменить
следующие константы:

.. code-block:: c++

  #define DISPLAY_CHARSET_HD44780 CYRILLIC

.. code-block:: c++

  #define LCD_FEEDBACK_FREQUENCY_DURATION_MS 0 //2
  #define LCD_FEEDBACK_FREQUENCY_HZ 0 //5000

И раскомментировать следующие константы:

.. code-block:: c++

  #define SDSUPPORT

.. code-block:: c++

  #define MKS_MINI_12864
