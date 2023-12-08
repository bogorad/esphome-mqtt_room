# esphome-mqtt_room
Use ESPHOME on M5stack-Atom-Lite to track iBeacons via Home Assistant's mqtt_room

 I have about a dozen M5stack-Atom-Lites around the house. Some of them run LD2420 radars, some run older LD1115H radars, and all of them are BT proxy modules for HA. I thought - why there's no integration with HA's `mqtt_room`?! So, I started investigating, and no luck. But I came across this piece of code:

https://github.com/rpatel3001/BleDistance

There aren't many things in life I hate as passionately as C++. I never fully understood the code, and it wasn't very useful as-is - the distance calculation when using HA android app (beacon) is crap.

But I learned from it and created a lambda that gets RSSI, negates it, and uses MQTT to send it to `mqtt_room` (instead of calculating the distance).

Unfortunately, there's no HA API for `mqtt_room`, so I had to use MQTT proper. Anyway, *my* code is crap, I haven't worked as a programmer since mid-90s :wink:, but it works, and if you want to make it better - have fun and let me know!

P.S. Ooops, I forgot - you need the include files from the project I shamelessly plagiarized. 

https://github.com/bogorad/esphome-mqtt_room
