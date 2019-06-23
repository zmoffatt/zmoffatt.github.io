---
name: SlugSat
tools: [Embedded C, Microcontrollers, ...]
image: /assets/SlugSat.jpg
description: Micro-satellite (cubesat) project with linear transponder and particle physics experiment.
---

# SlugSat

SlugSat is a fully student-designed and built microsatellite project completing its third year within the Electrical Engineering Senior Design Capstone at UC Santa Cruz. The mission of the satellite is to carry two payloads into low Earth orbit. The first is a linear transponder which enables amateur radio enthusiasts on the ground to make long-distance HF contacts without relying on atmospheric propagation. The second payload is an atmospheric research experiment monitoring for low-energy Terrestrial Gamma Ray Flash events, in partnership with Professor David Smith of the Santa Cruz Institute for Particle Physics. To support and control these payloads in orbit, the satellite also requires the auxiliary systems for Power, Attitude Control, and Command and Control. All elements of the system have been individually prototyped, and the full system integration has been completed. 

### Linear Transponder 

SlugSat’s primary payload, a linear transponder, is designed for amateur radio operators operating on the 10m/15m band to relay single-sideband voice and morse code signals. The transponder receives signals from radio operators at a frequency of 21.4MHz, converts it to a lower intermediate frequency of 10.7MHz for power stabilization, then mixes up to 29.4MHz for transmission. This payload should be able to receive a 21.4MHz signal of power down to -110dBm, and be able to re-transmit it at 29.4MHz at a power of +21dBm with a signal-to-noise ratio of at least 15dB. Over the course of the past year, great progress was made on this payload and it is close to meeting the aforementioned specifications. In its current state, the linear transponder meets all above specifications except for meeting the transmit power. Future work for this subsystem includes bringing all circuit prototypes up to their design specifications, as well as working on making the entire transponder system is robust enough to handle the harsh space environment.

### Terestrial Gama Ray Flash Detector

SlugSat’s secondary payload, the Terrestrial Gamma Ray Flash Detector Experiment, is a collaboration between SlugSat and the Santa Cruz Institute for Particle Physics. The system consists of four detectors, each capable of picking up x-rays with an energy down to 10 keV. A scintillator is physically coupled to each silicon photomultiplier to convert the x-rays into a signal that the system can then shape and convert to eight digital levels. In parallel, a real time clock system with microsecond accuracy will time tag the event and store the time and energy level into the system’s memory. This year the detector is sensitive to 60 keV and the ADC outputs four bits, while the real time clock remains entirely in the design stages. Next year will construct the real time clock and increase the sensitivity of the detector into its final design. 

### Power System

The power system is tasked with safely generating, storing, and distributing enough energy to power the satellite for its intended use case — running all systems 100% of the time, except for the Science Payload which runs 44% of the time. This year’s prototype successfully accomplishes this goal with a 20% energy headroom per orbit (ISS) by employing the following Electric Power System (EPS). Each face of the satellite is covered with 29.5% high-efficiency photovoltaics, producing on-average 4.5 watts through a Maximum Power-Point Tracking system. Power is then used to charge the 24Wh battery pack, capable of distributing power through each of the seven voltage rails when sunlight is eclipsed. A custom battery management system employs current-limiting short-circuit protection, and sends telemetry data to the onboard computer to facilitate the power-modes algorithm. In an effort to contextualize future design work, an energy budget report is provided for each of SlugSat’s three most-likely orbital paths. These reports in combination with the successfully prototyped power circuitry will allow future SlugSat engineers to implement all power-related circuitry onto a single PCB of appropriate size for the flight unit. 

### Attitude Estimation

The satellite must be able to orient itself within the pointing requirements of the payloads: less than 20 degrees from nadir pointing, or pointing towards the center of the Earth. To meet this requirement, SlugSat will use an Attitude Control System (ACS) that combines sensors, actuators, and feedback control algorithms to measure and change the satellite’s orientation in space. We designed and prototyped a proof-of-concept ACS which runs in hardware-in-the-loop simulations. Simulation results met the required specifications for the system: mean steady-state pointing error was measured at 2.10, 1.66, and 3.13 degrees in three simulated low Earth orbit paths. Sensor and actuator prototypes do not all currently meet their required specifications; these will need to be improved in the future. Additionally, the overall system needs optimization and improved robustness to handle hardware failure. 

### Distributed System

In order to facilitate the simultaneous operation of the payloads and auxiliary systems, the On-Board Computer (OBC) controls the state of the satellite and mediates both inter-satellite communications and communications between the satellite and ground. These communications must be error-free and all state transitions must be predictable, stable (states do not flicker), and must guarantee that the satellite remains functionally active at all times. SlugSat’s OBC consists of a distributed system of low-power microcontrollers running control modules specific to each subsystem’s and a telemetry system that implements a custom packet protocol to perform telemetry to ground communications. The system we prototyped allows all three microcontrollers to pass information without collision, responds to ground messages appropriately, and intelligently control power distribution to each of the other subsystems. The current OBC is a scalable platform that is ideal for future additions. While the control system meets the minimum specifications of the satellites operations, further optimization with regard to power and processing will be required in order to maximize payload operation time.

<img src="/assets/SlugSat/SlugSat_Team.jpeg" width="500">

<p class="text-center">
{% include button.html link="http://slugsat.soe.ucsc.edu" text="Learn More" %}
</p>