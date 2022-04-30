# Setup Instructions
Firstly, you'll need to print out all your parts. Like the Mini-AfterSherpa, you'll need to press two threaded inserts into the top of the shroud, but you'll also need to press two inserts in to the posts of the fan mount.

Before you do anything else, I would highly recommend watching this video from Vez3D: https://www.youtube.com/watch?v=E3kBau82SwU
The below image is pulled from it.
<img width="1334" alt="Screen Shot 2022-04-30 at 3 06 50 PM" src="https://user-images.githubusercontent.com/93737816/166124166-685a0327-5af3-42d9-935c-29a4c3455579.png">

I'm following his example by controlling my printer via a pin on the Pi, and in order to do that, we need to set up your Pi as a second MCU (https://www.klipper3d.org/RPi_microcontroller.html). But I have two differences when compared to his wiring. Firstly, in addition to having the grey wire connect to GPIO26, I also connect the black wire on the fan controller to a ground pin on my MCU (in my case an SKR Mini E3 V2). 
Secondly, In order to get a good signal from my control pin, I needed to put a low-pass filter between my fan's controller and my RPi and MCU. Shoutout to @ademuri on the Voron discord for the idea.

![RC-Low-Pass-Filter](https://user-images.githubusercontent.com/93737816/166124358-5a75a4ce-446e-4044-aa16-12f0d58c5985.png)

In this circuit diagram of a low-pass filter, the top wire is connecting GPIO26 to the fan controller, and the bottom wire is connecting your MCU ground to the fan controller. The input (left side in diagram) should be connected to your Pi and MCU, while the output (right side in diagram) should be connected to your fan controller. It should look something like this:
![IMG_4186 2](https://user-images.githubusercontent.com/93737816/166124532-96710c31-637f-4d27-a368-a54e0c64095f.JPG)

Add the connectors according to the finished wiring loom:
![IMG_4197](https://user-images.githubusercontent.com/93737816/166124548-bd6d72f8-fb3f-4af6-bbea-96309f3f34d6.JPG)

If you don't use 
![IMG_4198](https://user-images.githubusercontent.com/93737816/166124560-929e95d8-df47-4fa8-b108-b082f1d60aef.JPG)

Grab the 10k resistor, the 1uF cap, some wire, some heatshrink, all your connectors, and soldering iron + solder.

In your config, change "fan" to the below settings

<img width="216" alt="Screen Shot 2022-04-28 at 11 58 19 PM" src="https://user-images.githubusercontent.com/93737816/165898117-19b03a1c-e4a8-4704-80c5-b39b65fa33c3.png">
