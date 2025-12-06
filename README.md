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

## Step 1:
First I connected my distance sensor, you can see the connection in these pictures:![IMG_1259](https://github.com/user-attachments/assets/fa60f0f1-504e-45ce-bb5f-ecb005550bc8)
![image0](https://github.com/user-attachments/assets/bc68a392-3e71-4f75-89fa-b6b2a553997b)
I placed a red jumper wire onto the 5-volt power pin on the Raspberry Pi and connected the other end to the positive power rail on the breadboard to supply power to the ultrasonic sensor. I placed a black jumper wire onto a ground pin on the Raspberry Pi and connected it to the ground rail on the breadboard to complete the circuit.

I connected the white jumper wire from the Raspberry Pi’s GPIO24 pins to the Trig pin of the ultrasonic sensor so the Raspberry Pi can send a trigger signal. I then routed the blue jumper wire from the Echo pin of the ultrasonic sensor through the two resistors on the breadboard, creating a voltage divider that reduces the signal down to a safe voltage. I connected the other end of the blue wire to the GPIO23 pin on the Raspberry Pi so it can safely read the return signal.

These connections allow the Raspberry Pi to power the ultrasonic sensor, send a trigger pulse, and safely receive the echo signal for measuring distance.

## Step 2:
After connecting my distance sensor I connected the led. You can see the wiring in this picture:
![IMG_1255](https://github.com/user-attachments/assets/147d0e1e-0100-4c03-9668-0badbf07d58d)

