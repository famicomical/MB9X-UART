# MB9X-UART
Building this PCB would allow you to program the Fujitsu F2MC-16LX series processors using an RS-232C serial port connection. It uses a 12-pin connector for direct connection to the JVC DT-V series monitors and an optional 10-pin connection as described in Fujitsu documentation. Note: that programming the DT-V monitors requires a slight modification to the Signal PWB. 

![MB9X-UART.jpg]

The person assembling this board will need to procure their own USB to RS232-C cable and their own copy of the Fujitsu "FLASH MCU Programmer 16LX" software, which includes necessary proprietary info about the chips. I recommend installing [ISP-MB9X](https://isp-mb9x.sourceforge.net/) by Sergey Pinigin in addition to the Fujitsu software to have some more fine control over programming the chip.
