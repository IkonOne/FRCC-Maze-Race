---
layout: default
permalink: /robots/club-bot.html
---

# Club Roboticists

Welcome.  This page is directed specifically toward individuals who wish to build their own robots to race.

Rules for this event can be [found here](/rules/club-line-follower.html).

## Overview

This page has several objectives.  They are as follows:

1. Quickly introduce readers to the process of building a line following robot from scratch and touch on potential snags that may be hit.
2. Provide resources which readers can use to further knowledge and procure parts.
3. Provide a simple but effective project management framework to ensure that the project is completed in time.

## Table of Contents

1. [Basic Project Management](#basic-project-management)
2. [How to Build a Robot](#how-to-build-a-robot)
    1. [Microcontrollers](#microcontrollers)
    2. [Motors](#motors)
    3. [Sensors](#sensors)
3. [Resources](#resources)

## Basic Project Management

When given a non-trivial project that must be completed within a specific timeframe, it is often easiest to sit and think through the problem before attempting to start.  This will allow you to set milestones and spot potential problems before they arrise.

There are several skills in this method required to complete the project efficiently:

1. [Minimum Viable Product](#minimum-viable-product)
2. [Milestones](milestones)
3. [Define High Level Requirements](#define-high-level-requirements)
4. [Concept Ideas](#concept-ideas)
5. [Prototype](#prototype)
6. [Develop](#develop)

### Minimum Viable Product

The primary concern when completing a project is meeting requirements.  This is as true when you are completing your homework as it is when completing a project for work or a client.  So be sure that the first iteration of your completed project does that with as little work as possible.  When you approach a project like this you make sure that your customer is satisfied and that minimal time has been used.

However, that does not mean don't consider the future improvements.  You should.  Just don't implement them.  There are ways that you can design a final MVP that allows for improvement while still minimizing time investment.

### Milestones

The project due date is not the only date that matters.  It is important that you set milestones that must be achieved by specific dates to ensure that your project doesn't get delivered late.  Some example milestones for the club robot might be:

1. 4/6/2018 - Complete idea concepting and order components.
2. 4/13/2018 - Program microcotroller(MCU) for basic controls of motors and reading sensors
3. 4/20/2018 - Program MCU to follow the line, curves and crosses.
4. 4/26/2018 - Finish optimizing robot.

Personally, I prefer a pencil and paper gantt chart to visualize scheduling for small or medium projects.  They make it easy to break the high level requirements into smaller requirements and set completion dates for each.

### Define High Level Requirements

In this stage you will do just as the title suggests and devine your high level requirements.  These do not get down into the nitty gritty but try to ensure that all aspects of the project are accounted for.

Here is a basic list of requirements to get you started:

1. Create a robot that conforms to the rules.
2. The robot must be able to sense the line effectively.
3. The robot must be able to move and turn.
4. [Optional] The robot must be programmable.
5. The solutions employed must be simple to implement.

Don't spend too long here.  You can always come back and add/delete requirements.

### Concept Ideas

This is where you start to think about how you want your robot to resolve the defined requirements.  To complete this step, you will need to research on google, on this site and anywhere else that you can think of to come up with ideas.  Remember, there are billions of people on this planet and it is very likely that someone has already solved the specific problem you are trying to solve as well.  Use their knowledge just as you do in school.  The world is an oyster or something like that.

Concepted ideas might be:

* Use 2 gear motors to drive the car.
* Sketch out a rought idea of the layout of the car.
* List potential materials to use such as glues, fastening straps, bottle caps for wheels, etc.
* How might the sensors be layed out?  Are you using a premade sensor?

This proces is not the time to be opinionated.  Every idea is worth considering and it could be a good process to just write everything you come up with on a post-it and then organize them when done brainstorming.

### Prototype

Try out your ideas after you have concepted them.  Nobody wants to build an entire robot only to find out that the battery is too small to run the motors and the microcontrolls at the same time.  Be sure that each idea is actually feasible by prototyping it.  If it turns out that an idea doesn't work, try another one from your concepted ideas or concept new ideas.

The key idea here is to fail early and fail often.  The faster you fail, the faster you learn and the faster you progress.

So if one of the ideas you have is to drive motors using the analog pins on an Arduino, try that out before attatching the motors permanently to the robot.

### Develop

Finally build the robot.  By now, you should have a solid idea of what ideas you had that worked and can put them together to complete your project.  Do it.

## How to Build a Robot

A standard robot consists of three key modules, the microcontroller, the motors and the sensors.  For a first timer, it is best to either build a line follower using a kit.

**Kits**

* [Pololu 3pi](https://www.robotshop.com/en/pololu-3pi-robot-only.html#Specifications) (Not Arduino)
* [Jsumo](http://www.jsumo.com/followme-line-following-robot-kit)
* [Google](https://www.google.com/search?rlz=1C5CHFA_enUS697US697&ei=PLG_WtTkHcKIjwPf0LrYAg&q=line+tracking+arduino&oq=line+tracking+arduino&gs_l=psy-ab.3..0j0i22i30k1l9.1976.2832.0.3029.7.7.0.0.0.0.127.716.0j6.6.0....0...1c.1.64.psy-ab..1.6.715....0.2X8jOW4RFYE) Lot's of from scratch builds.

In the following sections, I will provide a basic overview of the key modules of the line following robot and some suggestions of what to get for those that would like to build their own robots.

### Microcontrollers

The ideal microcontroller to start out with is the Arduino.  It is easily programmable and there are tons of resources online that you can find.  I understand that some of you have Pi's, but I know next to nothing about Pi's...

The microcontroller is the brain of the robot.  In a line following robot, it will perform these functions:

* Read the sensors
* Determine where the robot is in relation to the line using the sensor data (position error)
* Drive the motors according to the calculated error

That is really it for a basic robot and is the best place to start.  There are robots that do nothing more than this that win contests.

##### Where to get an Arduino?

Ebay is your best bet.  They have kits that will give you everything you need to learn to use one.  Also remember that the line following kits above probably come with an Arduino as well, so if you get one of those, you probably don't need one of these.

* [Cheap Starter Kit 1](https://www.ebay.com/itm/Epal-Ultimate-UNO-R3-Starter-Kit-for-Arduino-1602LCD-Servo-Motor-LED-Relay-RTC/263099256052?hash=item3d41f00cf4:g:i4kAAOSwjSJaevIu:sc:ShippingMethodExpress!27870!US!-1)
* [Cheap Starter Kit 2](https://www.ebay.com/itm/UNO-R3-Ultimate-Starter-Kit-For-Arduino-LCD-Stepper-Servo-Ultrasonic-Motor-1602/253210291543?epid=1377694653&hash=item3af4826d57:g:p0sAAOSwYXVYx7KI)
* [Cheap Starter Kit 3](https://www.ebay.com/itm/Professional-UNO-R3-Starter-Kit-for-Arduino-Servo-LCD-Compass-Gyro-USA-Shipping/262647016789?hash=item3d26fb6d55:g:jCcAAOSwXf1aeweF:sc:ShippingMethodExpress!27870!US!-1)

### Motors

**[WARNING]** Motors(and Servos) can destroy your microcontroller!  They draw a lot of current and you need to protect your MCU with some sort of regulating circuit.

Here are some options that you can use to drive your motors.  All of these isolate the motor powersupply from the microcontroller to drive your motors:

* [L298N](https://www.ebay.com/sch/i.html?_odkw=arduino&_osacat=0&_from=R40&_trksid=p2045573.m570.l1313.TR8.TRC2.A0.H0.Xl298n.TRS0&_nkw=l298n&_sacat=0).
* [Ardumoto Shield](https://learn.sparkfun.com/tutorials/ardumoto-kit-hookup-guide?_ga=2.10223926.2023136451.1522506474-96889552.1515765240)
* [Ardumoto Shield Kit](https://www.sparkfun.com/products/14180?_ga=2.237128067.2023136451.1522506474-96889552.1515765240) comes with motors and wheels.

##### Types of Motors

My recommendation is to run with a [servo modified for continuous rotation](https://learn.adafruit.com/modifying-servos-for-continuous-rotation/overview) or a Brushed motor.  The servo is the easiest to control accurately but is generally a bit slow.  A brushed motor is normally going to be faster than a servo but it is harder to control accurately and will require gear reduction (more on that later).

###### Servos

Servos are generally designed to rotate only around 120 degrees instead of continuously rotating like a normal motor.  However, they can be modified by breaking a couple of mechanical blocks and soldering two resistors to the controllers.  Also, you can buy servos already modified.

Here are some continous rotation servos:

* [Pololu](https://www.pololu.com/category/143/continuous-rotation-servos)
* [HiTec](https://www.servocity.com/hsr-2645crh-servo)
* [Google](https://www.google.com/search?q=continuous+rotation+servo&rlz=1C5CHFA_enUS697US697&source=univ&tbm=shop&tbo=u&sa=X&ved=0ahUKEwjlvfbc65baAhVH1GMKHX3MDA8QsxgILA&biw=1440&bih=803)

###### Brushed Motors

Moving on to Brushed motors introduces a couple of new problems that Servos handle for you right out of the gate.

1. Their speed can be harder to control.
2. They require gear reduction to drive a wheel.

__Speed Control__

Brushed motors have optimal voltage ranges.  If they operate outside of those ranges, they loose torque and speed(and generate a ton of heat).  So you will want to use PWM to drive the motor.  [This tutorial relays the concept much better than I can](https://howtomechatronics.com/tutorials/arduino/arduino-dc-motor-control-tutorial-l298n-pwm-h-bridge/).

__Gear Reduction__

Brushed motors will often spin at thousands to tens of thousands of RPM's.  Attaching a wheel directly to the motor shaft would simply not work as a result.  The motor would be trying to spin the wheel too fast and the torque of the motor would be too small to actually spin it, so the motor would burn out and you would have to replace it.

To overcome this problem requires the use of gears.  This can be done by purchasing a motor with a gearbox on it, buying the gearbox itself or maybe using gears from an RC car parts supplier.

##### Brushed Motor Purchase Options

There are numerous sizes of brushed motors.  Pager motors and 130 size motors are possible solutions.  But really, you can probably make any motor work as long as you take the above issues into account.

* [Pololu Motors and Gearboxes](https://www.pololu.com/category/22/motors-and-gearboxes)
* [Basher Motors](https://hobbyking.com/en_us/130-size-brushed-rev-tuned.html) (These are likely just normal brushed motors with a nice label and some color.)
* [HobbyKing Motor Finder](https://hobbyking.com/en_us/motor.html)

### Sensors

Sensors come in many shapes and sizes.  The easiest way to get started with them is to get a prebuilt sensor board.  This will have documentation on how to use it with an arduino and will be just about plug and play.  It is relatively simple to develop your own board but without electronics experience, it would be time consuming to work out the details.

These sensors are nothing more than Infrared Reflectivity sensors.  I describe their functionality [here](/frcc-robot-race/robots/shield-bot.html#how-the-line-sensors-work) for those that are interested.

* [Pololu Line Sensors](https://www.pololu.com/category/123/pololu-qtr-reflectance-sensors)
* [Sparkfun Line Sensors](https://www.sparkfun.com/search/results?term=line+sensor)
* [Google](https://www.google.com/search?q=line+sensor&rlz=1C5CHFA_enUS697US697&source=univ&tbm=shop&tbo=u&sa=X&ved=0ahUKEwj5-vn28JbaAhVJ12MKHbj3BSwQsxgIKQ&biw=1440&bih=803)

## Resources 

Where to buy parts:

* [Pololu](https://www.pololu.com/)
* [Sparkfun](https://www.sparkfun.com/)
* [AdaFruit](https://www.adafruit.com/)
* [Ebay](https://www.ebay.com/)
* [Banggood](https://www.banggood.com/) (sometimes ships from china and takes forever)
* [AliExpress](https://www.aliexpress.com/) (maybe from china as well?)

Where to find tutorials and learn how to use things:

* [Learn Sparkfun](https://learn.sparkfun.com/)
* [Learn AdaFruit](https://learn.adafruit.com/)
* [Instructables](http://www.instructables.com/)
* [Makezine](https://makezine.com/)
* [Google](https://www.google.com/)