---
name: Mechatronics Autonomous Robot
tools: [Electrical, Solidworks]
image: /assets/Mech/robot.png
description: Autonomous robot capable of navigating a field, avoiding obstacles, locating and shooting an opponent. All before the opponent shot it.
---

# Mechatronics Autonomous Robot


## Challenge 
The robot had to start from one side of a 4ft by 8ft field called the Starting Zone, and drive to the other side of the field called the Initial Firing Zone, where the robot would be allowed to shoot ping pong balls at an opponent. There are lines of 2inch tape about half a foot along the inside of the field to allow robots to follow the tape and get to the other side. Lines of tape were also placed in the middle of the field in cross shapes, which also indicated where the obstacles could be located. 

## Obstacles 
The path to the Initial Firing Zone can be blocked with obstacles in the form of cacti that stood ten inches tall, ten inches wide, and three inches deep. These obstacles were fitted with beacons shooting 1.5kHz and 2.5kHz frequencies designed to confuse our beacon detector focused on 2kHz frequencies. These obstacles were also fitted with wires along the inside edges of the base of the obstacle to allow inductor circuits to detect their presence. There were three of these obstacles on the field that could be positioned on a line (not visible on the field) in front of the cross shapes of the center tape. These obstacles can be on the tape-following lines which made navigation of the robot more challenging. These obstacles were spaced apart from each other in such a way that a robot that was maxed out in volume could still fit in between the obstacles. 

## Design Overview
The robot consists of a circular design and two planes for the electronics and the launcher to sit inside. There is a tower in the center of the robot extending to eleven inches above the surface. Much of these design choices were made to fit in The Cube of Compliance, which was an 11x11x11 inch cube. 

The circular base is 10 inches in diameter, which allows the robot to easily be within The Cube of Compliance, and will make sure the robot doesn't hit anything while turning corners. If we had a square base, the corners of the bot may collide with the obstacles during a turn. The underside of the robot has the tape sensors, bump sensors, and two skids made out of half of a ping pong ball. 

The first floor of the robot holds most of the electronics that do the sensing and control for the bot. The UNO Stack, H-bridge, and driver boards for the sensors sit inside the robot, and two motors are on the sides of the robot for driving. 

On the second floor, there is the ping pong ball launcher, which has a custom mount for holding the pitching motors and being attached to the PVC T-fitting. There is a tower in the middle of the robot that holds the beacon, and two prongs that hold the beacon detector cone. 

<img src="/assets/Mech/robot.png" width="250">

<img src="/assets/Mech/Beacon.png" width="500">

<img src="/assets/Mech/BeaconCone2.png" width="250">

<img src="/assets/Mech/Tape_Sensor.png" width="500">

<img src="/assets/Mech/Track_Wire.png" width="500">

## Launcher

The ball launcher was designed remembering that it has to shoot the ping pong ball roughly sixteen feet if both our robot and the opponent robot is on their respective sides of the Initial Firing Zone. Many teams had chosen to use the counter-rotating wheels, but we were skeptical of the current draw of having two motors spinning continuously and potentially blowing fuses on the Uno Stack. We would also need a third motor to get balls into the counter-rotating wheels. Initially tried to use a spring-loaded mechanism to fire the ball as seen in Figure \ref{fig:PDR}. After prototyping the design and testing it, the ball could only go about 6 feet, and each shot was not very accurate.

<img src="/assets/Mech/wheelloader.png" width="500">

After seeing that many teams were using counter-rotating wheels with little to no trouble, we switched to that mechanism. After some time on SolidWorks and some laser-cut parts out of MDF, we created a simple mount for the motors and redesigned part of the failed spring-loaded prototype to act as the ball plunger to push the balls into the wheels. There is a slider piece that act as the plunger, and a long hole vertical with a pin allows the mechanism to turn rotation motion in to linear oscillation. When the plunger is pulled back, the next ball loads from gravity, and then the plunger pushes the ball in between the pitching motors to make it launch. The benefit of this design is that the motors can just continuously run in a single direction, which means a pin can just have a PWM signal in software. This worked tremendously well, and even at a duty cycle of 10-20\%, we were easily getting the range we needed. The three motors were controlled using the DS3658 Driver board. 

<img src="/assets/Mech/Built_Launcher.jpg" width="500">

<img src="/assets/Mech/robot.png" width="500">

<img src="/assets/Mech/robot_real.jpg" width="500">