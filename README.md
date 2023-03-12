# MB9X-UART
Allows you to program the Fujitsu F2MC-16LX series processors using an RS-232C serial port connection. It uses a 12-pin connector for direct connection to the JVC DT-V series monitors and an optional 10-pin connection as described in Fujitsu documentation. Note: [programming the DT-V monitors](dt-vmod) requires modifying the Signal PWB. 

![PCB](MB9X-UARTsmall.jpg)

The person assembling this board will need to procure their own USB to RS232-C cable and their own copy of the Fujitsu "FLASH MCU Programmer 16LX" software, which includes proprietary configuration files for the MCUs. I recommend installing [ISP-MB9X](https://isp-mb9x.sourceforge.net/) by Sergey Pinigin in addition to the [Fujitsu software](http://web.archive.org/web/20041020161858/http://www.fme.gsdc.de/products/utilitie.htm) to have some more fine control over programming operations.

## Example Usage
 - Identify the chip you are programming and set the DIP switches accordingly
   - Settings can be found in Fujitsu documentation. The /CS and RTS switches should stay ON.
 - Connect the USB-RS232C port to the assembled MB9X-UART PCB
    - extension of the USB cord is preferable to extending the RS232-C connection. in other words, connect the MB9X-UART directly to your adapter.
 - Connect the MB9X-UART to your target board, and turn on the power
 - Invoke the ISP-MB9X program from the command-line. 
   - For example: ```isp-mb9x.exe /1 /o4 /MB90F553A /b ROM.mhx /r```
uses serial port COM1 to dump the ROM from a Fujitsu MB90F553A running at 4MHz into a file called ROM.mhx
      - Caution: running the program without the /r command will erase the ROM from your MCU by default, so be careful!!
 - Wait for the read to complete being careful not to disturb the cables.
 - Power off your equipment and unplug the board

