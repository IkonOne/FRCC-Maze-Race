---
layout: default
---

# Shield Bot

The Shield Bot is the free to use robot for FRCC Students.  The robot is based on the [Parallax Shield Bot](https://www.parallax.com/product/130-35000) but there are some key differences described below.  You must be an FRCC Student to use the ShieldBot in the races.

# Specifications

I have attempted to compile information on the electronic components that are on the schools Shield Bot.

* 1 x [Arduino Uno Rev. 3](https://store.arduino.cc/usa/arduino-uno-rev3)
* 1 x [Parallax Board of Education Arduino Shield](https://www.parallax.com/product/35000)
* 1 x [Parallax Ping))) Ultrasonic Distance Sensor](https://www.parallax.com/product/28015)
* 2 x [Sharp GP2Y0A21YK0F IR Distance Sensor 10-80 cm](https://www.parallax.com/product/28995)
* 4 x [ON Semiconductor QRB1134](https://www.digikey.com/product-detail/en/on-semiconductor/QRB1134/QRB1134-ND/187533) ([Datasheet](http://users.ece.utexas.edu/~valvano/Datasheets/QRB1134.pdf))
* 2 x [Parallax Continuous Rotation Servos](https://www.parallax.com/product/900-00008)
* 1 x [Arduino Starter Kit](https://store.arduino.cc/usa/arduino-starter-kit)

# Usage

If you have never used an Arduino before, it is strongly recommended that you complete chapters 0, 1, 2 and 5 in the Project Book included in the Arduino Starter Kit.  After completing these projects, you will have been exposed to the basics of input and output on the Arduino, basic electronics theories and basic Servo control.  You are now ready to learn to control the Shield Bot.

This is a guide of the key concepts that you must acquire to learn to turn the Shield Bot into a line following monster.  The concepts are presented in an order that should build on itself but they are not all inclusive.  There are likely to be some skills that are missing that you may need to hunt down.  [Google](https://google.com), [Learn Parallax](https://learn.parallax.com/) and [Arduino Tutorials](https://www.arduino.cc/en/Tutorial/HomePage) are a great place to start your search.

1. Complete chapters 0, 1, 2 and 5 in the Project Book included in the Arduino Starter Kit.  **The Arduino should remain connected to the robot.**
2. [Ensure the servos are connected correctly.](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-2-shield-lights-servo-9)
3. [Test the servos.](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-2-shield-lights-servo-4) ([Part 1](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-2-shield-lights-servo-3), [Part 2](https://learn.parallax.com/tutorials/robot/shield-bot/robotics-board-education-shield-arduino/chapter-2-shield-lights-servo-2))
4. [Learn to use the line sensor.](https://www.pololu.com/docs/0J19)

You should now have the experience necessary to move the Shield Bot along the line.

# Take it to the Limit

* [Use millis for timing instead of delay.](https://learn.adafruit.com/multi-tasking-the-arduino-part-1/using-millis-for-timing)  This will let you multitask since delay is a blocking function so that you can update the motor speed in real time.
* [Use Finite State Machines to control the line sensor and the state of the robot.](http://gameprogrammingpatterns.com/state.html)
* [Use a PID control loop to steer the robot smoothly.](https://www.robotshop.com/letsmakerobots/pid-tutorials-line-following-0)

# Resources

* [Arduino Tutorials](https://www.arduino.cc/en/Tutorial/HomePage)
* [Arduino API](https://www.arduino.cc/reference/en/)
* [Learn Parallax](https://learn.parallax.com/)
* [Sparkfun Tutorials](https://learn.sparkfun.com/tutorials)
* [Fritzing Circuit Simulator](http://fritzing.org/home/)
* [Platform IO](https://platformio.org/) (A crossplatform IDE/Toolchain that makes it possible to [debug](http://docs.platformio.org/en/latest/plus/debugging.html) projects)