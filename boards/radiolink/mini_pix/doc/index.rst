.. zephyr:board:: radiolink_minipix

Overview
********

The Radiolink Mini-Pix Board is drone controller
board featuring the STM32F405VG, see `STM32F405VG website`_.
This is the 64-pin variant of the STM32F405x series,
see `STM32F405x reference manual`_. More info about the controller available
on `radiolink`_.

Hardware
********

TBD


Supported Features
==================

The Zephyr Mini-Pix board configuration supports the following
hardware features:

+------------+------------+-------------------------------------+
| Interface  | Controller | Driver/Component                    |
+============+============+=====================================+
| NVIC       | on-chip    | nested vector interrupt controller  |
+------------+------------+-------------------------------------+
| SYSTICK    | on-chip    | system clock                        |
+------------+------------+-------------------------------------+
| UART       | on-chip    | serial port                         |
+------------+------------+-------------------------------------+
| GPIO       | on-chip    | gpio                                |
+------------+------------+-------------------------------------+
| PINMUX     | on-chip    | pinmux                              |
+------------+------------+-------------------------------------+
| FLASH      | on-chip    | flash                               |
+------------+------------+-------------------------------------+
| SPI        | on-chip    | spi                                 |
+------------+------------+-------------------------------------+
| I2C        | on-chip    | i2c                                 |
+------------+------------+-------------------------------------+
| ADC        | on-chip    | ADC Controller                      |
+------------+------------+-------------------------------------+
| USB OTG FS | on-chip    | USB device                          |
+------------+------------+-------------------------------------+

The default configuration can be found in
:zephyr_file:`boards/radiolink/mini_pix/radiolink_minipix_defconfig`

Pin Mapping
===========

Default Zephyr Peripheral Mapping:
----------------------------------

- UART_1 TX/RX :
- UART_2 TX/RX :
- I2C1 SCL/SDA :
- USER_PB :
- USER_LED :

Clock Sources
-------------

The board has two external oscillators. The frequency of the slow clock (LSE) is
32.768 kHz. The frequency of the main clock (HSE) is 8 MHz.

The default configuration sources the system clock from the PLL, which is
derived from HSE, and is set at 168MHz, which is the maximum possible frequency
to achieve a stable USB clock (48MHz).

Programming and Debugging
*************************

There are 2 main entry points for flashing STM32F4X SoCs, one using the ROM
bootloader, and another by using the SWD debug port (which requires additional
hardware). Flashing using the ROM bootloader requires a special activation
pattern, which can be triggered by using the BOOT0 pin.

Flashing
========

TBD

References
**********

.. target-notes::

.. _radiolink:
   https://radiolink.com.cn/doce/index.html

.. _dfu-util:
   http://dfu-util.sourceforge.net/build.html

.. _STM32F405VG website:
   https://www.st.com/en/microcontrollers-microprocessors/stm32f405vg.html

.. _STM32F405x reference manual:
   https://www.st.com/resource/en/reference_manual/rm0090-stm32f405415-stm32f407417-stm32f427437-and-stm32f429439-advanced-armbased-32bit-mcus-stmicroelectronics.pdf
