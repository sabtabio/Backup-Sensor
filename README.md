# Backup-Sensor

These are the instructions to create your own distance indicator device using a Raspberry Pi, and HC-SR04 ultrasonic distance sensor, and LEDs. The device measures distance in real time and uses LEDs to display how close an object is.

Components Needed:

* Raspberry Pi
* Breadboard
* 1 x LED
* 4 x male to female jumper cables
* 2 x 330 ohm resistors
* 1 x 470 ohm resistor
* 1 x HC-SR04 ultrasonic distance sensor

This schematic shows how I wired my breadboard to the Raspberry Pi:
<img width="462" height="314" alt="Fritzingfinal" src="https://github.com/user-attachments/assets/339d444a-beb9-4401-a470-050822cac9de" />

Step 1:
First I connected my distance sensor, you can see the connection in these pictures:![IMG_1259](https://github.com/user-attachments/assets/fa60f0f1-504e-45ce-bb5f-ecb005550bc8)
![image0](https://github.com/user-attachments/assets/bc68a392-3e71-4f75-89fa-b6b2a553997b)
I placed a red jumper wire onto the 5-volt power pin on the Raspberry Pi and connected the other end to the positive power rail on the breadboard to supply power to the ultrasonic sensor. I placed a black jumper wire onto a ground pin on the Raspberry Pi and connected it to the ground rail on the breadboard to complete the circuit.

I connected a blue jumper wire from the Raspberry Pi’s GPIO pins to the Trig pin of the ultrasonic sensor so the Raspberry Pi can send a trigger signal. I connected a white jumper wire from another GPIO pin on the Raspberry Pi to the Echo pin (through the voltage divider on the breadboard) so the Raspberry Pi can safely read the return signal without exceeding 3.3 volts.

These connections allow the Raspberry Pi to power the ultrasonic sensor, send a trigger pulse, and safely receive the echo signal for measuring distance.
