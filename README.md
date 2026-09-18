UR5e Industrial Automation Capstone
Overview
This repository contains the source code, logic structures, and demonstration media for a three-phase industrial robotics capstone project using Universal Robots (UR5e). The objective across all modules is to design safe, continuous, and state-driven automated sequences by developing custom control logic and bypassing pre-packaged template scripts.

Tools Used: UR Studio (PolyScope X), UR5e Collaborative Robot, Digital I/O Sensors & Actuators.

🛠 Task 1: Pick & Place Process Enhancement
Objective: Automate a continuous 5-part packaging and conveyor sorting sequence.

Logic Architecture: Bypassed the template's default background scripts to build a custom continuous loop. Utilized an integer counting variable (blocks_n_box) to track payload status.

I/O Synchronization: An embedded If statement executes a state-machine handshake once the 5-block limit is reached.

Actuators & Sensors:

DO 2 (Stopper Gate): Driven LO to release the full box, HI to catch the empty box.

DI 1 (Proximity Sensor): Verifies box presence to prevent dropping blocks onto an empty moving belt.

partInBox (Boolean): Manually toggled to activate/deactivate conveyor rollers.

⚙️ Task 2: Machine Tending Automation
Objective: Develop a modular, state-driven sequence to safely load, machine, and unload raw parts into a CNC Lathe.

Modular Programming: Refactored a linear sequence into isolated global functions (Load_Machine and Unload_Machine) to meet strict modularity standards.

Machine Handshake: The Main Program acts purely as a master loop coordinating the I/O signals between the robot and the CNC machine.

Sequence Flow:

Call Load_Machine (Robot picks part, places in chuck, closes door).

Set DO 0 = HI (Trigger Lathe cycle).

Execute a 5.0-second delay for machining.

Set DO 0 = LO (Stop Lathe).

Call Unload_Machine (Robot opens door, extracts finished part, places in tray).

🏗 Task 3: Custom Work Cell Design
Objective: (Placeholder: Design a custom robotic environment addressing specific safety, reach, and cycle-time constraints.)

Logic Architecture: (To be updated upon completion)

I/O Synchronization: (To be updated upon completion)

Key Features: (To be updated upon completion)


Demos of each project can be accessed in the drive folder: https://drive.google.com/drive/folders/18FROj5r9rTD9KrIasNdUdKXYqurgthB3?usp=sharing
