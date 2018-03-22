---
layout: default
permalink: "/shield-bot/"
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

If you have not yet figured out how to program the Shield Bot, be sure to complete the [Hello World](#hello-world) step first.

For this step, you will need the Shield Bot with the Arduino attached, the Arduino programming cable and a computer that you can program the Arduino with.

Let's start.

The first step is to ensure that the sensors are hooked up correctly.  Please refer to the [Sensor Wiring](#sensor-wiring) section to verify this.

Now, create a new Arduino sketch and copy the following code in.  Make sure that you read the comments and understand the code.

```cpp
/**
 *
 *   _________.__    .__       .__       .___       __________        __  
 *  /   _____/|  |__ |__| ____ |  |    __| _/       \______   \ _____/  |_
 *  \_____  \ |  |  \|  |/ __ \|  |   / __ |  ______ |    |  _//  _ \   __\
 *  /        \|   Y  \  \  ___/|  |__/ /_/ | /_____/ |    |   (  <_> )  |  
 * /_______  /|___|  /__|\___  >____/\____ |         |______  /\____/|__|  
 *         \/      \/        \/           \/                \/             
 * 
 * @author  Erin M. Gunn
 * @email   ikonone@gmail.com
 * @description A tutorial to familiarize students with the FRCC Shield Bot.
 * 
 * Directions: Read the comments from top to bottom.  Be sure to complete
 * the activities at the bottom.
 */

#include <Arduino.h>

/**
 * These constants rename the Arduino pins that the sensors
 * are plugged into so that our code is easier to read.
 */
const int PIN_IR_EMITTERS = A5;
const int PIN_IR_SENSOR1 = A1;
const int PIN_IR_SENSOR2 = A2;
const int PIN_IR_SENSOR3 = A3;
const int PIN_IR_SENSOR4 = A4;

/**
 * Print an array to the Serial console.
 * 
 * @param   arr     An array of type T where T is anyhting that can be printed by Serial.
 * @param   arrSize The size of the array.
 */
template <class T>
void printArray(T arr[], int arrSize) {
    Serial.print("{ ");
    for(int i = 0; i < arrSize; i++) {
        Serial.print(arr[i]);
        if(i < arrSize - 1)
            Serial.print(", ");
    }
    Serial.println("}");
}


/**
 * This is the first function called by the Arduino.
 * It is only called once.
 */
void setup() {
    Serial.begin(9600);

    /**
     * Before using the line sensor, we must configure the Arduino
     * so that it knows how we will be using the pins that the sensor
     * is connected to.  We do that using pinMode.
     * 
     * With pinMode, we can tell the Arduino that we will use a pin
     * as either an input or output.  Trying to use a pin that was
     * set as an output as an input pin will yield funky results.
     * For this reason, it is best to avoid toggling pins as much
     * as possible.
     */

    // Configure line sensor pins.
    pinMode(PIN_IR_EMITTERS, OUTPUT);
    pinMode(PIN_IR_SENSOR1, INPUT);
    pinMode(PIN_IR_SENSOR2, INPUT);
    pinMode(PIN_IR_SENSOR3, INPUT);
    pinMode(PIN_IR_SENSOR4, INPUT);

    /**
     * The brightness of the sensors is controlled by setting the 
     * value parameter of analogWrite to any integer between [0, 255].
     * 
     * 0 is off.
     * 255 is full bright.
     * 
     * This does not work by simply changing the amount of
     * electricity flowing to the IR Emitters.  It is actually
     * using Pulse Width Modulation (PWM).  This is not necessary
     * to understand now, but there is more information in the docs 
     * for the curious.
     * 
     * https://www.arduino.cc/reference/en/language/functions/analog-io/analogwrite/
     */

    // Turn on the IR Emitter.
    analogWrite(PIN_IR_EMITTERS, 255);
}

void loop() {
    /**
     * The IR Sensors allow varying amounts of voltage to pass through
     * them depending on how much infrared light is hitting them.  We
     * can read the amount of voltage that is passing through the sensor
     * using the built-in Analog to Digital Converter (ADC).
     * 
     * Arduino.h provides analogRead to allow us to do just that.  We
     * simply pass it the correct pin number and it returns a value 
     * between [0, 1023] that corresponds to the current voltage.
     * 
     * In our case, a return value of 0 is 0 volts and a return value
     * of 1023 is 5 volts.  Different microcontrollers (MCU) may measure
     * different voltage ranges.  More information is in the docs for
     * the curious.
     * 
     * https://www.arduino.cc/reference/en/language/functions/analog-io/analogread/
     */

    // Read the values of the sensors.
    int sensor1 = analogRead(PIN_IR_SENSOR1);
    int sensor2 = analogRead(PIN_IR_SENSOR2);
    int sensor3 = analogRead(PIN_IR_SENSOR3);
    int sensor4 = analogRead(PIN_IR_SENSOR4);

    // print the sensor values to the serial console.
    const int sensorValues[] = { sensor1, sensor2, sensor3, sensor4 };
    printArray(sensorValues, 4);
}

/**
 * Now run the code.
 */

/**
 * Activities (Yay!! \o/ )
 * 
 * 1. Try putting different objects in front of the sensors to see
 *      how the values change.  Which colors or materials lower the
 *      values and which raise them?  Do the values ever reach the
 *      documented minimum or maximum (see analogRead docs)?
 * 
 * 2. Using the crappy whiteboard demo track, output to the serial
 *      console using Serial.println which sensor the line is under.
 *      Then if the line is under 2 sensors, print both.
 *      Now print every sensor which the line is under.
 *      (Hint: It could be under all 4 sensors)
 * 
 * BONUS: Figure out where the center of the line is under the sensors 
 * in code.  This is a non-trivial problem that introduces several 
 * electrical and mechanical issues.  The main electrical issue is
 * that the sensors don't ever reach their real minimum or maximum
 * values and each sensor is different from the one next to it.  The
 * mechanical issue is the sensors are not evenly spaced so you will
 * likely not ever be able to knoe _exactly_ where the center is
 * unless it is between the middle sensors.
 */
 ```

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