|=-----=[ Lonely example ]=-----=|

This application starts by checking the real-time scheduling by activating task1 wich 
will activate and launch task3 before terminating itself (this will print 123 (for the 3 
steps) on the lcd).
Task2 is activated by an autostart alarm (with a period of 1s) and blinks the lcd light.
If you press B1 then "B1 pressed" is displayed on the lcd.
If you press B2 then "B2 pressed" is displayed on the lcd.

This application tests the drivers for the timers (timer0 to initialize lcd and timer1 
with IRQ for systemcounter) and the lcd in the same time.
It also checks the externals interrupts on the two push buttons.

Usage:
1 - Install openOCD and the D2XX drivers (OR libusb AND libftdi as you want) in order to 
communicate with the JTAG

2 - Configure the application with
'''
goil --target=arm/olimex_lpc_l2294 -v --templates=../../../../goil/templates/ lonely.oil
'''

3 - Upload your program into the board :
- by opening the OPENOCD communication --> click on 2-run-openocd.command
- and launch your program --> click on2a-debug-external-ram.command for example