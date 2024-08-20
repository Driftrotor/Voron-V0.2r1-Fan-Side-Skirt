# Voron V0.2r1 Fan Side Skirt
 Add a touch of cooling to your skirts

----

A simple Fan Skirt designed to fit neatly with the OEM style skirts for the Voron V0.2r1

![Skirt 1](https://github.com/user-attachments/assets/e1753681-44a3-47b6-ac9e-df994f808252)

Using 3010 fans to add a little cooling power to the Z Stepper Motor and Power Supply to keep it all running happily!
Fans are press fit into the skirts so no need for screws.

----

Fan covers are press fit onto the front of the fans aiding in a seemless look.
There are TWO versions of Fan Covers to choose from, Version 2 is slightly quieter.
Also for each Fan Cover there is a NORMAL and TIGHTER fit to make sure they fit your fans nicely. 

----

From experience i found that running the fans (if you have 2) reduced the chamber temparture significantly, especially if you have ACM panels.
I have found that 50% Fan is adequate to keep things cooler under the skirts without affecting chamber temps.

~~~
[heater_fan Skirt_Fans]
pin: expander:PA0
max_power: 1.0
kick_start_time: 0.5
heater: extruder, heater_bed
heater_temp: 45.0
fan_speed: 0.5
~~~
Add this to your ```Printer.cfg``` or ```Klipper Expander.cfg``` - Just remeber the change the ```PIN:``` to your output pin

```heater``` sets what will activate the Skirt Fans - The provided config is set so that either the Bed Heater or Extruder Heater will active the Skirt Fans.
```heater_temp``` will set the temperature that the Skirt Fans will turn off at.

>if you have both ```extruder``` and ```heater_bed``` set Klipper will keep the Skirt Fans on until both have cooled down to the set temperature.

```fan_speed``` will set the fan speed with ```1``` being 100% and ```0``` being 0% / off.

----

> [!NOTE]
>the config is set in a way that it automates the Skirt Fans so that when the printer is idle and below the set temperature the Skirt Fans will be off as the power supply will not be under load so not generating a lot of heat. once a load is applied from turning on the heaters the fans will be activated.
