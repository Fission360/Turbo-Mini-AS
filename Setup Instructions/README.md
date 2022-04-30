# Print Your Parts
Firstly, you'll need to print out all your parts. Like the Mini-AfterSherpa, you'll need to press two threaded inserts into the top of the shroud, but you'll also need to press two inserts in to the posts of the fan mount. Set up your hotend as you did on your original one, ommitting the part cooling fans and mounting the Sherpa Mini to the top. 

# Mounting the Fan
Take your three M2.5x12 screws and screw them from the back of the mount and into the posts on the fan. Then, mount the fan to the panel with two M3x6 screws. Run the wires under the small slot in the bottom of the panel and zip tie them from the inside. Finally, route the fan's connector and wires through the motor panel with the boweden tube and everything. It should look something like this when you're done:

![IMG_4202](https://user-images.githubusercontent.com/93737816/166125307-f4efa567-0cfe-4296-bb0e-34fc8cb27dda.JPG)
![IMG_4204](https://user-images.githubusercontent.com/93737816/166125303-e32165b5-f81a-4c79-b4bc-82e06df6600d.JPG)


# Hook Up the Tubing
You'll need two lengths of CPAP for this step, one x long (we'll call it tube 1) and the other y long (this will be tube 2). Tube 1 will connect the CPAP fan outlet adapter to the hose connector, and tube 2 will connect the hose connector to the fan itself. The hose connector will be mounted in front of the opening in the motor panel with double-sided tape (I wouldn't recommend using VHB tape here; it will be a pain in the butt to remove should you need to take off the motor panel). In order for the tube to bend in the correct way, you'll need to twist one end of each tube on the connector, so that the tube moves in the desired fashion. Add some electrical tape to the smaller ends of the fan outled adapter, so that you get a snug fit into the shroud. Final result will look like this:

![IMG_4205](https://user-images.githubusercontent.com/93737816/166125676-aac620ad-7a52-4bb0-99d7-344b151d18c4.JPG)
![IMG_4206](https://user-images.githubusercontent.com/93737816/166125679-ff2c3d28-6510-479c-8f33-5d99993d7767.JPG)
![IMG_4176](https://user-images.githubusercontent.com/93737816/166125730-5c5238b4-60d7-4f31-9bed-a2c7e861b78b.JPG)


# Wiring
Before you do anything else, I would highly recommend watching this video from Vez3D: https://www.youtube.com/watch?v=E3kBau82SwU
The below image is pulled from it.

<img width="1334" alt="Screen Shot 2022-04-30 at 3 06 50 PM" src="https://user-images.githubusercontent.com/93737816/166124166-685a0327-5af3-42d9-935c-29a4c3455579.png">


I'm following his example by controlling my printer via a pin on the Pi, and we need to set up the Pi as a second MCU for klipper to recognize the pin. (https://www.klipper3d.org/RPi_microcontroller.html). I do have two differences when compared to his wiring. Firstly, in addition to having the grey wire connect to GPIO26, I also connect the black wire on the fan controller to a ground pin on my MCU (in my case an SKR Mini E3 V2). 
Secondly, In order to get a good signal from my control pin, I needed to put a low-pass filter between my fan's controller and my RPi and MCU. Shoutout to @ademuri on the Voron discord for the idea.
![RC-Low-Pass-Filter](https://user-images.githubusercontent.com/93737816/166124358-5a75a4ce-446e-4044-aa16-12f0d58c5985.png)

In this circuit diagram of a low-pass filter, the top wire is connecting GPIO26 to the fan controller, and the bottom wire is connecting your MCU ground to the fan controller. The input (left side in diagram) should be connected to your Pi and MCU, while the output (right side in diagram) should be connected to your fan controller. Wiring up the 10k resistor and the 1uF cap like the diagram will look similar to this:

![IMG_4186 3](https://user-images.githubusercontent.com/93737816/166124846-36db728c-7955-4b6a-9fbf-baaf72c8e721.JPG)

Cover the resistor and cap leads with heatshrink, and add the connectors according to the finished wiring loom. I took the 6-pin JST connector from the fan's included potentiometer, but inserted my own crimps:

![IMG_4199](https://user-images.githubusercontent.com/93737816/166125031-1123b220-4155-49a9-a44d-e925de431653.JPG)

Here it is fully wired up; the dupont connector goes to GPIO26, the 2-pin JST goes to a spare port and connects to ground, and the 6-pin JST plugs back into the fan controller:

![IMG_4201](https://user-images.githubusercontent.com/93737816/166125167-22911d3c-5f96-422b-882c-b67940304e25.JPG)


In your config, change "fan" to the below settings and restart your firmware; I've found that for my particular setup, these settigns allow me to go as low as 10-12% without the fan skipping.

<img width="216" alt="Screen Shot 2022-04-28 at 11 58 19 PM" src="https://user-images.githubusercontent.com/93737816/165898117-19b03a1c-e4a8-4704-80c5-b39b65fa33c3.png">

Now you should be ready to print!
