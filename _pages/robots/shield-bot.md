---
layout: default
permalink: /robots/shield-bot.html
---

# Shield Bot

The Shield Bot is the free to use robot for FRCC Students.  The Shield Bot is based on the [Parallax Shield Bot](https://www.parallax.com/product/130-35000) but there are some key differences described below.  You must be an FRCC Student to use the ShieldBot in the races.

## Specifications

I have attempted to compile information on the electronic components that are on the schools Shield Bot.

* 1 x [Arduino Uno Rev. 3](https://store.arduino.cc/usa/arduino-uno-rev3)
* 1 x [Parallax Board of Education Arduino Shield](https://www.parallax.com/product/35000)
* 1 x [Parallax Ping))) Ultrasonic Distance Sensor](https://www.parallax.com/product/28015)
* 2 x [Sharp GP2Y0A21YK0F IR Distance Sensor 10-80 cm](https://www.parallax.com/product/28995)
* 4 x [Fairchild QRB1134](https://www.digikey.com/product-detail/en/on-semiconductor/QRB1134/QRB1134-ND/187533) ([Datasheet](http://users.ece.utexas.edu/~valvano/Datasheets/QRB1134.pdf))
* 2 x [Parallax Continuous Rotation Servos](https://www.parallax.com/product/900-00008)
* 1 x [Arduino Starter Kit](https://store.arduino.cc/usa/arduino-starter-kit)

## How does it work?

The brain of the Shield Bot is the Arduino.  An Arduino is a microcontroller development board with easy to use electronics and software that can read inputs and outputs to perform actions such as check if a button is down or send a Tweet.  In our case, the Arduino is attached to the larger Board of Education Shield which has some additional hardware that makes it safe and easy to read the sensors and power the servos.

## How do I make it work?

Great question.  And fear not, it's actually quite simple.  There are three key steps that we will follow to get you going.

* [Hello World](#hello-world)
* [Learn to use the line sensors.](#learn-to-use-the-line-sensors)
* Learn to drive the servo motors.

I will be getting you through these steps as quickly as I can.  My guess is that it will take around 1 hour to complete the setup process.

### Hello World

For the obligatory Hello World program you will need the Shield Bot with the Arduino attached, the Arduino programming cable and a computer that you can install software on.

Now that you have the required hardware, complete [Activity 1](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-1-your-shield-bots-21) and [Activity 2](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-1-your-shield-bots-18) of [Chapter 1](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-1-your-shield-bots-19).  Finally, review the [Summary](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-1-your-shield-bots-4).

### Learn to use the line sensors.

After completing this tutorial, you should be able to:

* Turn on and off the line sensor emitters.
* Read values from the line sensors.

If you have not yet figured out how to program the Shield Bot, be sure to complete the [Hello World](#hello-world) step first.

For this tutorial, you will need the Shield Bot with the Arduino attached, the Arduino programming cable and a computer that you can program the Arduino with.  Once you have everything, verify that the sensors are hooked up correctly.  Please refer to the [Sensor Wiring](#sensor-wiring) section to verify this.

##### How the line sensors work

The line sensor is composed of 4 [QRB1134](https://www.digikey.com/product-detail/en/on-semiconductor/QRB1134/QRB1134-ND/187533) sensors and a custom PCB that allows the values of the sensors to be read and can turn on and off all of the emitters.

The emitters in the QRB1134 are simply LED's that emit Infrared Light.  It is like a fancy type of Infrared light bulb.  The more electricity we send through it, the brighter it is.

The sensors are a special electrical component called a phototransistor.  This is like the opposite of a light bulb.  The more light hits it, the more electricity it lets pass through.

We use these sensors by turning on the emitter, putting something in front of the sensor and then reading how much light bounces back.  The amount of light is a function of two variables:

1. How close the object is to the sensor. (The optimal distance is around 5mm)
2. How much infrared light the object reflects.  (White objects reflect more than black)

```
EMITTER          SENSOR
      \/        /\
       \        /
        \      /
         \    /
          \  /
           \/
+---------------------+
```

##### How to actually use the sensors

Create a new Arduino sketch and copy the following code in to the sketch.  Be sure to read and understand all of the comments.

If you experience any issues, please reach out either on the FRCC CSClub's discord or [comment directly on the gist here](https://gist.github.com/IkonOne/c6ab3e4a82d7c0e36aa74e1925899b93).

{% gist c6ab3e4a82d7c0e36aa74e1925899b93 %}

## Take it to the Limit

These are some suggestions on where to look for ideas on how to make the Shield Bot faster.  The point of the competition is to win right?

* [Use millis for timing instead of delay.](https://learn.adafruit.com/multi-tasking-the-arduino-part-1/using-millis-for-timing)
* [Use Finite State Machines to control the line sensor and the state of the robot.](http://gameprogrammingpatterns.com/state.html)
* [Use a PID control loop to steer the robot smoothly.](https://create.arduino.cc/projecthub/mjrobot/line-follower-robot-pid-control-android-setup-e5113a)

## Resources

* [Arduino Tutorials](https://www.arduino.cc/en/Tutorial/HomePage)
* [Arduino API](https://www.arduino.cc/reference/en/)
* [Learn Parallax](https://learn.parallax.com/)
* [Sparkfun Tutorials](https://learn.sparkfun.com/tutorials)
* [Fritzing Circuit Simulator](http://fritzing.org/home/)
* [Platform IO](https://platformio.org/) (A crossplatform IDE/Toolchain that makes it possible to [debug](http://docs.platformio.org/en/latest/plus/debugging.html) projects)