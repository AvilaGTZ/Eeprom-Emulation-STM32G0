

martes, 3 de marzo de 2020
10:07 p. m.

# Eeprom-Emulation-STM32G0
EEPROM emulation for ST low cost devices

# What
Stm32G0 series is a very low cost embedded microcontroller, and does not have EEPROM memory
To store data, wich means that if you want to save some values permanently, you should use the
Flash memory. This is a basic driver for that.

# How it works?
First of all, we will use a ST Nucleo board: STM32G071 #
https://www.st.com/en/evaluation-tools/nucleo-g071rb.html

The functionality is basic, an array of three values will be stored on the memory flash, emulating a EEPROM, then once blue built in button is pressed, the data will be retrieved from the flash and will be printed via USART
We will allocate an specific page of the flash, so our data can be retrieved always from the
Same memory place, and our program will never touch that memory section.

The lenght of ach page on ST32G0 series is 2k 
We will use page 31 (address 0X0800FFF)

# Board configuration
	Clock frec             = 16Mhz
USART-------------------------
	Selected USART  = USART2
	Baud rate       = 115200
	GPIO's          = PA2(Tx), PA3(Rx)
	
Trigger button -------------------

GPIO            = PC13 (Built in blue button)
