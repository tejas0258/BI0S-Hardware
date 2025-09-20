
## 7 Segment Display
To use this without a library I had to make use of a 2-D array. 
The array was made of values for individual leds for the numbers and then the these values for different numbers.
A list was made to which kept all track of all the pins of the Display which were conencted to the ESP.
I used a nested for loop to iterate through the array. 
- The first for loop was used to iterate between the data for different leds.
- The second loop iterates to get the individual values for different leds for the number.
- then in the second loop I use the value of the control variable of the loop to access the pins.Then I check if the value from the array is 0 or 1 and assign the values accordingly.

*I could try to make use of hex values to streamline this code even further.

## Sequence LED:
A list of pin mapping was made. In the programming, I made a loop to make ith pin of the of the list high and evertyhing else to low.

*one could use bit shift method also but that one felt more complicated.
## LCD Display:
I knew the basic pinout of the LCD connections. So I made the basic circuit and connected all the data pins with a pull down resistor to a slide switch. Then Backlight connections were made and and for contrast pin I connected it to ground directly.
A input switch was added at the E pin and the RS pin. (pulldown)
After this I had to follow the youtube video of Mitch Davis on how to run a lcd without a microcontroller.
All the connections were pretty much the same except a capacitor on the E pin pushbutton and the potentiometer to control the contrast.
The push button was connected to a capacitor because in real life scenarios the push button bounces a bit and this can create irregular signals which can cause the lcd to read the wrong data. The capacitor helps mitigate this issue.
Then some basic initialising commands were shown. The video showed the method to initialise in 4 bit mode.

## Servo Clock
For this I used the ServoEsp32 library for controlling servos.
I made the connections to the servo made a for loop to control the angle of the servos based on the time passed.
## Baremetal Programming
Wasted a lot of time on this. Followed many videos but many were teaching way too complicated stuff and that too for STM32 and the ones those who were teaching bare metal for arduino only taught the basic code for blinking a LED.
I understand the part till blinking an LED. But taking a analog input and the using PWM is a bit too complicated task and I could not find any sources for this on the internet. I tried reading the documentation for Atmega 328, STM 32, ESP32, Github docuementation also for bare metal.
I still did not get anywhere near in getting an analog input.
I thought of looking at the source code of arduino files to see what the digitalwrite and read functions do in the background. I understood some bits but then whole thing was interlinked with other functions which made the task of reaching to the bottom of the program difficult.
Finally used the normal blinking led program to generate a pwm signal to control the angle of a servo.
