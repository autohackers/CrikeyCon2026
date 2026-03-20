## Porsche 2004 CAN dashboard & RPi

This area is for files relating to the RPi + PiCAN that powers the dashboard from a Porsche 996/986 series vehicle.


# Commands (RPi terminal)
There is a `candump-date.log` file in this folder. This is a capture of the CAN bus, from inserting the key, ingition and driving around the block once. So watching it play back using `canplayer -I candump.log` on the dashboard will show you exactly what the dashboard in the car was displaying at the time.

If you want to send individual blocks of data (eg)
`cansend can0 12A#001000323403450a`
 
# Speedo

The speedo (tachometer) can be addressed as the target `2A8` on the canbus.
To send values to the speedo use

`cansend can0 2A8#FFFFA80E0F6DEFFF`

The value in this example is ~88mph.

You may note that the speedo needle only twitches towards the actual value. This is due to the refresh rate - the speedo should actually receive a constant set of values, like:

```
2A8#FFFFA80E0F6DEFFF
2A8#FFFFA80E0F6DEFFF
2A8#FFFFA80E0F6DEFFF
2A8#FFFFA80E0F6DEFFF
2A8#FFFFA80E0F6DEFFF
2A8#FFFFA80E0F6DEFFF
```

The quick way of doing this is to make a loop, such as encapsulating the cansend command like

`while true; do  cansend can0 2A8#FFFFA80E0F6DEFFF; done;`

This can be seen in the `88mph.script`

# Thermostat

The CAN code for the thermostat on this dashboard is `289` and the 2nd byte is the value being displayed. From my research (eg rennlist forums) the formula for the 2nd byte is (where X is the value to be displayed, in Celsius) is (4614+(167*X))/100 (noting this is decimal and the output needs to be converted to HEX).

So to display 100 C on the dashboard

`while true; do cansend can0 289#00D5000000000000; done;`

Reference [Rennlist Forum link](https://rennlist.com/forums/996-gt2-gt3-forum/966928-looking-for-can-bus-information-2.html) about half way down.

# No Buffer Space Error

If you get the 'no buffer space' error when using the PiCAN a reboot will generally fix this. However a better fix is (after a reboot) changing the buffer length with: 

`sudo ifconfig can0 txqueuelen 1000`

This fix has already been done on first boot however if the problem reoccurs, please reboot and run the above command.
Further info [Stack overflow](https://stackoverflow.com/questions/40424433/write-no-buffer-space-available-socket-can-linux-can)

