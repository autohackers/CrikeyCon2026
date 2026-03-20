## Porsche 2004 CAN dashboard & RPi

This area is for files relating to the RPi + PiCAN that powers the dashboard from a Porsche 996/986 series vehicle.


# Commands (RPi terminal)
There is a `candump-date.log` file in this folder. This is a capture of the CAN bus, from inserting the key, ingition and driving around the block once. So watching it play back using `canplayer -I candump.log` on the dashboard will show you exactly what the dashboard in the car was displaying at the time.

If you want to send individual blocks of data (eg)
`cansend can0 12A#001000323403450a`
 
