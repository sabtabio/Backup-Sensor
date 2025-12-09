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
First I connected my distance sensor, you can see the connection in these pictures:
![IMG_1259](https://github.com/user-attachments/assets/fa60f0f1-504e-45ce-bb5f-ecb005550bc8)
![image0](https://github.com/user-attachments/assets/bc68a392-3e71-4f75-89fa-b6b2a553997b)
I placed a red jumper wire onto the 5-volt power pin on the Raspberry Pi and connected the other end to the positive power rail on the breadboard to supply power to the ultrasonic sensor. I placed a black jumper wire onto a ground pin on the Raspberry Pi and connected it to the ground rail on the breadboard to complete the circuit.

I connected the white jumper wire from the Raspberry Pi’s GPIO24 pins to the Trig pin of the ultrasonic sensor so the Raspberry Pi can send a trigger signal. I then routed the blue jumper wire from the Echo pin of the ultrasonic sensor through the two resistors on the breadboard, creating a voltage divider that reduces the signal down to a safe voltage. I connected the other end of the blue wire to the GPIO23 pin on the Raspberry Pi so it can safely read the return signal.

These connections allow the Raspberry Pi to power the ultrasonic sensor, send a trigger pulse, and safely receive the echo signal for measuring distance.

## Step 2:
After connecting my distance sensor I connected the led. You can see the wiring in this picture:

![IMG_1255](https://github.com/user-attachments/assets/147d0e1e-0100-4c03-9668-0badbf07d58d)

I placed a resistor that lines up with the cathode of the LED light, preventing the LED light from drawing too much power. I then connected a male-to-female jumper cable (Black cable) from the ground pin 39 to the breadboard. I placed another male-to-female jumper cable to align with the anode of the LED light, I have that cable connected to GPIO 17 on the Raspberry Pi.

## Step 3:

Once everything has been connected we have to create the code for the sensor. You can fine my code for the sensor here:
<https://github.com/sabtabio/Backup-Sensor/blob/72e09309d7a6f8e621395dfd6df3f7e2eeefa26c/maincode>.
To make an executable program open your terminal and type "nano filename.py". YOu can name it whatever you like, I named it backupsensor.py. What this does is creates a file under whatever you named it and enters the text editor. Now you can copy and paste my code from the link above then save and the editor. You can see the file I created as well as what the text editor looks like below.
<img width="1278" height="673" alt="python code" src="https://github.com/user-attachments/assets/33534a84-e233-46ed-b34d-b886be3a8908" />
<img width="1278" height="728" alt="fullpython" src="https://github.com/user-attachments/assets/5159fd95-f1a8-4b76-9640-e03b81be8e63" />

## Step 4:

The file should now be executable, to run this file in the terminal just type in "python filename.py". 
<img width="1277" height="672" alt="runcode" src="https://github.com/user-attachments/assets/58c418d6-4b2d-4dc9-b8e1-26051821090e" />
Once the code is running, the distance sensor will activate the LED whenever an object is detected within 100 cm. The LED will flash at a slow rate at this distance, increase its flashing speed at 50 cm, and flash even faster at 25 cm. When the object is closer than 10 cm, the LED will remain steadily on. You can see in the video below how it should be properly running.
https://youtube.com/shorts/0DFrfmVFYmA?si=4LSVcP_dTi8ToJwT
