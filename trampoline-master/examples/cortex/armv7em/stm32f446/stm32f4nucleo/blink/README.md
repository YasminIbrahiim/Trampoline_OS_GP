|=-----=[ Blink example ]=-----=|

This application is a simple periodic example wich toggles the blue led of the board.
Have a look into "blink.oil" file.

The system is based scheduled with a 1ms SysTick "SystemCounter".

The task "blink" toggles the BLUE led when executed.
This is not scheduled when the program starts.

This task is activated by the alarm "blink_blink".
This alarm starts 250ms (ALARMTIME) after "StartOS".
This alarm has a 250ms (CYCLETIME) period.

Configure the application with

`
goil --target=cortex/armv7em/stm32f446/stm32f4nucleo --templates=../../../../../../goil/templates/ blink.oil
`
ldflags += "--no-warn-rwx-segments".split() --add this line to build.py line 143
