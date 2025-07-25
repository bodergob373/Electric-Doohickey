---
title: Electric Doohickey
author: Jonathan Itoh
description: A prototype electric vehicle to gain experience and design the electric system of an ethanol-electric hybrid I want to build in the future (and to build a fun go-kart). It's an array of 20 Nissan Leaf batteries managed by a BMS to power a 12kW hub motor (or a temporary hoverboard motor until I could afford it).
created_at: 2025-06-25
---



# June 25th: Research

In order to use one of the 12kW 72V hub motors that I want to use for the full car, I need powerful batteries that can continuously output 167A. I looked at battery cells to buy, but I would need 150 of them. They're expensive and I don't want to wire them all together, so I decided to search for used EV batteries.

**Total time spent: 2h**



# July 1st: Metal
I looked around for scrap pipes and found curved segments of an old trampoline frame. I tore it apart, measured the segments, set up the 3D workspace, and modeled them. I had a hard time modeling the curve so I measured the pipe's length, made a circle with a circumference 12 times that, and got a 12th segment. Because they're curved, an oval frame would be simple.

<img width="760" height="282" alt="image" src="https://github.com/user-attachments/assets/df0f76e1-5b29-4815-ae1b-31632df111d2" />

**Total time spent: 5h**



# July 2nd: Designing
I measured parts the 10" wheels and modeled them. I also got their inner diameter and found that Home Depot had perfect 5/8" threaded rods. Then, I measured the battery modules, double checked them with online dimensions, and modeled them. I looked at how batteries are usually wired in series and parallel and made the 10S2p design with the battery modules.

<img width="1123" height="453" alt="image" src="https://github.com/user-attachments/assets/1255c5e5-6742-4925-9e81-59eaeea75094" />

**Total time spent: 3h**


# July 3rd: Designing 2
Using bus bars that go across the batteries in a straight line would be simpler, so I rotated every other parallel group and added bus bars. For the kart, I decided to use 4 curved segments in an oval. For simplicity, the steering is only 1 wheel. It's not a bike so I put the other wheels on the sides to keep it upright. I designed the fork, arranged the frame quarters, positioned the seat and steering, added foot bars, designed the battery frame, and put the side wheels at an angle.

<img width="548" height="534" alt="image" src="https://github.com/user-attachments/assets/2394ea89-692a-4d8e-85ec-62e094b01b79" />
<img width="687" height="478" alt="image" src="https://github.com/user-attachments/assets/580fec52-80c0-479a-b8d8-3108bfc945ef" />

**Total time spent: 4h**



# July 4th: Research 2
Found crimp terminals for connecting the motor to the motor controller. 

**Total time spent: 5h**



# July 6th: Research 4
Apparently, another motor controller from the same company is both better and $60 cheaper than the one I already found. 

**Total time spent: 5h**



# July 7th: Designing 3
I modeled the motor controller.

<img width="307" height="235" alt="image" src="https://github.com/user-attachments/assets/df3e2a76-d058-4dd0-bd2e-f32f3a1b62d2" />

**Total time spent: 0.5h**



# July 8th: Designing 4
To simplify battery mounting and wiring, I put all the batteries in one stack supported by threaded rods on three crosspipes of the frame. I also modeled the BMS, shunt resistor, both contactor sizes, the hub motor, and the twist throttle. To fit the twist throttle to the pipe, I designed a 3D printable adapter that it could fit around. Then, I added angled pipes to connect the stabilizers to the frame. For the rear wheel, I would need a strong way to mount the hub motor on the frame, but that would result in gross angles between the mounting pipes and the curved sides of the frame. I used this as an opportunity to add a swing arm with nice 90 degree angles connected to the frame with a threaded rod, holes, and nuts. For suspension, I put leftover trampoline compression springs under the swing arm so that they would stretch when the suspension is compressed. Finally, I started the wiring design by connecting the motor controller to the hub motor.

<img width="719" height="459" alt="image" src="https://github.com/user-attachments/assets/72e9d44b-d560-433d-b72c-2f87114a0ac3" />

**Total time spent: 9h**



# July 9th: Designing 5
I modeled the pre-charge resistor and designed all the wiring. To strengthen the stabilizers and make them easier to build, I removed their tilt and put them both on a threaded rod. I also designed the steering to actually work by havoing a pipe that rotates inside another and supports the lower half of the fork. A threaded rod connects it to the handle with nuts and shaft collars. Because I can't buy the $700 hub motor now, I want to use a hoverboard wheel temporarily because the voltage and current limits of the motor controller can be set. So that I can keep all the metal parts the same, I designed a 3D printable mount that allows the hoverboard wheel to be attached to the swing arm lower down. 

<img width="828" height="399" alt="image" src="https://github.com/user-attachments/assets/04100db1-b3bb-4c02-8aae-8f335b30d122" />
<img width="532" height="606" alt="image" src="https://github.com/user-attachments/assets/78a9d577-12d6-4686-ab93-2aff7a32f86a" />
<img width="370" height="329" alt="image" src="https://github.com/user-attachments/assets/cb04b18b-43ea-4afa-980f-1a1d77457623" />

**Total time spent: 7h**



# July 10th: Part Sourcing
I continued looking for parts such as wires and terminals. I would need 2/0 or 1/0 AWG silicone wire to handle the battery amps but it's like $7 per foot. I researched low-cost conductors and found that solid aluminum bars are cheap and lightweight with the only drawbacks of size and flexibility. I replaced the copper bus-bars in my design with slightly thicker and wider aluminum bars and found the right sizes online, saving $20. I still want to eliminate all thick wiring for other parts in the final design.

<img width="848" height="652" alt="image" src="https://github.com/user-attachments/assets/ed1b6f06-f32a-4436-995a-4049498f9fe1" />

**Total time spent: 2h**



# July 11th: Final Design
To replace all 2/0 AWG silicone wiring with solid aluminum, I extended the ends of the bus-bars and put the contactors and resistors on them. 

<img width="848" height="652" alt="image" src="https://github.com/user-attachments/assets/ed1b6f06-f32a-4436-995a-4049498f9fe1" />

mrbeast for scale

<img width="518" height="531" alt="image" src="https://github.com/user-attachments/assets/4d7e2d95-6c98-4e06-bfb2-49e9e2292dc9" />

**Total time spent: 2h**



# July 15th: Wiring Diagram
Made the wiring diagram in Google Drawings

<img width="982" height="614" alt="image" src="https://github.com/user-attachments/assets/7aa6ef37-77ff-418a-b222-751268ab48f1" />

**Total time spent: 3h**



# July 16th: BOM
Made the BOM in Google Sheets

<img width="626" height="680" alt="image" src="https://github.com/user-attachments/assets/7fb7395c-9c94-411c-80a3-9fd59ba256ab" />

**Total time spent: 2h**



# July 21st: Metal 2
Moved all the metal pipes into the garage, then scrubbed and hosed them down. Then, I bought the threaded rods, nuts, and washers from Home Depot.

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/f6db236b-7d8a-4079-a67b-fdeb73096dad" />

**Total time spent: 5h**



# July 22nd: Cutting
Because I have a limited number of straight short tubes and longer straight ones were slightly bent, I planned out what pipes will be cut and where. Before I will start cutting them, I laid the main frame quarters together and confirmed the dimensions. Then, I cut off the ends of them so that they could be easily be connected and be stronger.

<img width="257" height="421" alt="image" src="https://github.com/user-attachments/assets/8929b37c-2a8c-4fac-b6ff-b05d5ba521fc" />

**Total time spent: 4h**
