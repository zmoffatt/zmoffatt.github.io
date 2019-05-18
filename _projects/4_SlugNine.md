---
name: SlugNine
tools: [Embedded C, Microcontrollers, Mechanical Systems, Matlab]
image: /assets/SlugNine/Walk.jpg
description: Small canine inspired robot created for a graduate bio-inspired locomotion class.
---

# SlugNine

In this paper, we present a novel paraplegic autonomous quadruped robot named "SlugNine" based on a canine inspired body. Autonomous quadrupeds have been in development since the early 2000s and at this point come in a wide range of sizes with different applied gaits. Rather than creating another autonomous quadruped, we aim to explore an alternative style of locomotion capable of being utilized by a quadruped in the event of a system failure or ''paraplegic disability'' that will allow autonomous quadrupeds to be able to still fulfill its mission on it's two front legs if the back legs become disabled. This alternative gate is based on quadrupedal animals that have successfully adapting to paraplegic disabilities, in particular, canines. Through active simulation and prototyping we examine the feasibility of SlugNine's locomotion up a ramp while carrying a fragile payload. Through active simulation and prototyping we examine the feasibility of SlugNine's locomotion up a ramp while carrying a fragile payload.

<img src="/assets/SlugNine/FBD.png" width="500">

Once the initial concept of the robot was settled on, two free body diagrams of the system was created to help guide the creation of models and simulations. The free body diagram seen above simplified the system down to three parts; a body and two leg rods connected to each other and the body by pivots. Considering the torque needed to lift the block mass vertically enough for forward movement, the force F is found by establishing the mass of the block, and the length of the torso in this case. 

<img src="/assets/SlugNine/Simscape.JPG" width="700">

The first step in creating a physical prototype of SlugNine was the creation of a virtual 3D CAD model using the MathWorks SimScape Multibody 2017b Toolbox. Simscape Multibody formulates and solves the equations of motion for the complete mechanical system through using blocks representing bodies, joints, constraints, force elements, and sensors. The model was defined as a trapezoidal block with two forward arms and a dragging base. The friction, damping, stiffness, and density were all modeled with approximate values similar to canines. The system model for SlugNine can be seen above, which incorporated the use of revolute joints on the articulations of the dog legs. The four corners of the feet as well as the back of the robot were modeled with spherical contact force planes to implement force feedback.

<img src="/assets/SlugNine/Shoulder.JPG" width="500">

Constraining movement of the humerus to be biaxial is a relevant in both the model and the physics behind our model due the the simplicity of the scope. To allow for different angles of engagement in the scapula joint, the scapula and humerus CAD is set up to be modular, to test these. We use plastics; specifically ABS, Polycarbonate, and Medium Impact Acrylic, because of their relative lightness and ease to shape, as well as fishing line for simplicity in the actuating the muscles.

<img src="/assets/SlugNine/Forelimb.jpg" width="700">

In the end the similarities between the robotic leg and the canine leg that inspired it can be seen above. The four major regions of the leg; the scapula, humerus, radius and toe, are all represented along with motors and fishing line to act on muscles on the acrylic 'bones'. Each muscle has an opposite to create the pulling pair found in animals, this allows for a more accurate bio-locomotion that closely mimics the movements of actual canines.

<img src="/assets/SlugNine/Walk.jpg" width="500">

While SlugNine demonstrates a mechanical system for increasing the survivability of quadrupedal robots following damage, that is one of many potential applications. Software based solutions have been developed to work on this same issue for robots, but not for living organisms. A hybrid system that takes advantage of the strengths of both mechanical and software controls solutions would be very useful and warrants further research. 
