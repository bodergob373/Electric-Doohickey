---
title: Electric Doohickey
author: Jonathan Itoh
description: A custom go-kart powered by 6 Nissan Leaf battery modules. It is driven by two hoverboard motors. The throttle sends signals to a microcontroller, which sends adjusted signals to both motor controllers. The rear wheels are on a suspension arm.
created_at: 2025-06-25
---
**total time spent: 76h**


# June 25th: Research
In order to use one of the 12kW 72V hub motors that I want to use for the full car, I need powerful batteries. I looked at battery cells to buy, but I would need a lot of them. They're expensive and I don't want to wire them all together, so I searched for used EV/hybrid batteries. I found listings for battery modules from both a Toyota Prius and Nissan Leaf. I decided to use the Leaf batteries because they're cheaper and more commonly used.

<img width="432" height="457" alt="module-from-nissan-leaf-gen-2-24kwh" src="https://github.com/user-attachments/assets/e3d02869-ed65-406d-ba0b-df983bca6675" />

**Total time spent: 4h**



# June 26th: Research 2
I thought that because they're from a car, maybe I could only use one module with smaller motors. After researching the nominal voltage, I would need more because they're only 8.4V. If I want to keep using the powerful motor, I would need 9 modules. It turns out that their nominal voltage is around 7.2V, so I would actually need 10 in series. The battery also needs to supply enough current for the motor. 12000kW / 72V is 167A, so I will need more battery modules in parallel. I chose to have 4 modules in parallel for the full car with 2 motors, so this kart with only 1 motor should only have 2 in parallel. It's still not enough to run at 12kW continuously, but it could maybe supply enough for a few seconds during acceleration.

<img width="770" height="384" alt="Screenshot 2025-08-07 174306" src="https://github.com/user-attachments/assets/77ce9c60-ec3e-40d3-b709-b9800f1b6fc3" />


**Total time spent: 3h**



# June 28th: Research 3
I found the motor controller. It's liquid-cooled and can handle 150A continuous at 72V. I researched parts of a liquid cooling system, but I realized it probably won't be using too much continuous current.

**Total time spent: 3h**



# June 28th: Batteries
I bought 30 Nissan Leaf batteries and made sure they worked.

<img width="521" height="693" alt="image" src="https://github.com/user-attachments/assets/b1956cce-2fbf-4269-ad9c-8be8d3ea8042" />

**Total time spent: 3h**



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



# July 4th: Research 4
Found crimp terminals for connecting the motor to the motor controller. I started researching what BMS I need. Only one voltage-sensing lead is needed per parallel group, so I would need a 10S BMS that can handle high amps. Many people use Orion BMS, but they're $400-$800. I spent a while lookimg for BMS units on Aliexpress and couldn't find many. I also wasn't completely sure whether I actually need only one for the whole battery pack or one per series string. The only one I found that might work could be an ANT BMS.

![ANT-BMS-10S-24S-50A-180A-Smart-32V-88V-Lifepo4-li-ion-LTO-Battery-Protection-Board-Double-PCBA-2](https://github.com/user-attachments/assets/723f1aea-5b29-462f-b28b-832fc12c61e1)
![71Gar08qu2L _SX522_](https://github.com/user-attachments/assets/2b0f8fe0-b058-4843-8f0c-7d8c5004843d)


**Total time spent: 5h**



# July 5th: Research 5
I realized that the Nissan Leaf modules each have 4 cells in a 2S2P configuration, so a 10S BMS wouldn't even work well. I also found out that the mysterious third terminal between the positive and negative terminals is due to the 2S and is required for voltage sensing. So instead, I will need a 20S BMS. I searched Aliexpress again and found a company that has many different BMS units and found a 25S BMS. I went back to Aliexpress and searched for the same model and found a slightly cheaper one. The BMS requires outside charge, discharge, and pre-charge contactors. I found a 500A contactor.


**Total time spent: 4h**



# July 6th: Research 6
Apparently, another motor controller from the same company is both better and $60 cheaper than the one I already found, so I will use that. The pre-charge contactor does not need to handle as much current, so I found a smaller and cheaper contactor. The 500A contactors I found disappeared so I will use ones that the BMS seller also has. The wiring diagram in the BMS manual also shows that a pre-charge resitor is needed. I calculated the required resistance and found a chassis-mount resistor that can handle the current. I also calculated the cross-sectional area of copper I need for the bus bars on the positive and negative terminals. The bus bars for the voltage-sensing terminals only need to be cheap and wide enough to bolt onto the terminals. I was able to find enough copper at good sizes for a decent price. Then, I found M4 and M6 brass bolts and screws for the battery terminals. For wiring, I found 20 AWG silicone wire for voltage sensing and 8 AWG silicone wire for the motor controller. 2/0 AWG silicone wire is way too expensive.

<img width="451" height="454" alt="Screenshot 2025-08-07 173133" src="https://github.com/user-attachments/assets/c88ee5b1-a8d8-47f9-9412-95e69d433779" />
<img width="464" height="453" alt="Screenshot 2025-08-07 173106" src="https://github.com/user-attachments/assets/3d46b909-0bdb-4a96-8338-025a3b8f4180" />
<img width="673" height="190" alt="Screenshot 2025-08-07 173437" src="https://github.com/user-attachments/assets/7bdbd304-b725-42f3-919f-080a8ee5bbc9" />

**Total time spent: 6h**



# July 7th: Designing 3
I modeled the motor controller.

<img width="307" height="235" alt="image" src="https://github.com/user-attachments/assets/df3e2a76-d058-4dd0-bd2e-f32f3a1b62d2" />

**Total time spent: 0.5h**



# July 9th: Designing 4
To simplify battery mounting and wiring, I put all the batteries in one stack supported by threaded rods on three crosspipes of the frame. I also modeled the BMS, shunt resistor, both contactor sizes, the hub motor, and the twist throttle. To fit the twist throttle to the pipe, I designed a 3D printable adapter that it could fit around. Then, I added angled pipes to connect the stabilizers to the frame. For the rear wheel, I would need a strong way to mount the hub motor on the frame, but that would result in gross angles between the mounting pipes and the curved sides of the frame. I used this as an opportunity to add a swing arm with nice 90 degree angles connected to the frame with a threaded rod, holes, and nuts. For suspension, I put leftover trampoline extension springs under the swing arm so that they would stretch when the suspension is compressed. Finally, I started the wiring design by connecting the motor controller to the hub motor.

<img width="719" height="459" alt="image" src="https://github.com/user-attachments/assets/72e9d44b-d560-433d-b72c-2f87114a0ac3" />
<img width="882" height="460" alt="Screenshot 2025-08-07 173654" src="https://github.com/user-attachments/assets/db58b152-0c9c-45f6-93fb-ffdeb93bd8df" />
<img width="626" height="407" alt="Screenshot 2025-08-07 173717" src="https://github.com/user-attachments/assets/c3deb327-5fdb-4091-9e82-85d4bf7ea538" />

**Total time spent: 9h**



# July 10th: Designing 5
I modeled the pre-charge resistor and designed all the wiring. To strengthen the stabilizers and make them easier to build, I removed their tilt and put them both on a threaded rod. I also designed the steering to actually work by havoing a pipe that rotates inside another and supports the lower half of the fork. A threaded rod connects it to the handle with nuts and shaft collars. Because I can't buy the $700 hub motor now, I want to use a hoverboard wheel temporarily because the voltage and current limits of the motor controller can be set. So that I can keep all the metal parts the same, I designed a 3D printable mount that allows the hoverboard wheel to be attached to the swing arm lower down. 

<img width="828" height="399" alt="image" src="https://github.com/user-attachments/assets/04100db1-b3bb-4c02-8aae-8f335b30d122" />
<img width="532" height="606" alt="image" src="https://github.com/user-attachments/assets/78a9d577-12d6-4686-ab93-2aff7a32f86a" />
<img width="370" height="329" alt="image" src="https://github.com/user-attachments/assets/cb04b18b-43ea-4afa-980f-1a1d77457623" />

**Total time spent: 7h**



# July 11th: Part Sourcing
I continued looking for parts such as wires and terminals. I would need 2/0 or 1/0 AWG silicone wire to handle the battery amps but it's like $7 per foot. I researched low-cost conductors and found that solid aluminum bars are cheap and lightweight with the only drawbacks of size and flexibility. I replaced the copper bus-bars in my design with slightly thicker and wider aluminum bars and found the right sizes online, saving $20. I still want to eliminate all thick wiring for other parts in the final design.

<img width="848" height="652" alt="image" src="https://github.com/user-attachments/assets/ed1b6f06-f32a-4436-995a-4049498f9fe1" />

**Total time spent: 2h**



# July 15th: Final Design
To replace all 2/0 AWG silicone wiring with solid aluminum, I extended the ends of the bus-bars and put the contactors and resistors on them. 

<img width="848" height="652" alt="image" src="https://github.com/user-attachments/assets/ed1b6f06-f32a-4436-995a-4049498f9fe1" />

mrbeast for scale

<img width="518" height="531" alt="image" src="https://github.com/user-attachments/assets/4d7e2d95-6c98-4e06-bfb2-49e9e2292dc9" />

**Total time spent: 2h**



# July 16th: Wiring Diagram
Made the wiring diagram in Google Drawings

<img width="982" height="614" alt="image" src="https://github.com/user-attachments/assets/7aa6ef37-77ff-418a-b222-751268ab48f1" />

**Total time spent: 3h**



# July 17th: BOM
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



# August 3rd: Redesign
Redesigned and simplified the wiring and model

**Total time spent: 2h**



# August 4th: Cutting 2
Cut all these pipes and made all the holes with a pipe notcher, drill, and angle grinder.

<img width="880" height="633" alt="image" src="https://github.com/user-attachments/assets/d31e8ff0-4d15-4886-88c5-2c3460bf7e34" />

**Total time spent: 7h**



# August 5th: Welding (images from after assembling)
Welded the main curved frame pipes together

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/c254145b-e787-4c66-8465-e04f7c66a0c1" />

Welded the middle crossbeam

<img width="1021" height="769" alt="image" src="https://github.com/user-attachments/assets/25a3f8e5-b2f2-48d4-b402-25a845a372a6" />

Welded the rear swing arm

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/3d2463f8-a99c-4790-ab0e-5a12160a773c" />

Welded the frame for mounting the seat

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/98658b2e-1b77-4e30-baee-5834f1e47b70" />

Welded the front fork

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/62e51f2a-27c7-494d-a52d-c0a46a3b0032" />

**Total time spent: 6h**



# August 6th: Welding 2
Welded the rear crossbeam

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/8e4a1c41-67c4-48b2-92e4-b2b32a2f95e4" />

Welded the front crossbeam

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/b80ba932-fca1-4a66-b209-d0ab9e7c69e3" />

Welded the frame for the seat to the vehicle frame with short pipes between

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/32ca4eec-5e64-49d1-a1c7-8dd62d117399" />

Welded the front footrest and front fork mount

<img width="1021" height="769" alt="image" src="https://github.com/user-attachments/assets/79ca9ebb-1de9-47ae-8b4d-9e1727d51f6d" />

Welded a pipe for reinforcing the fork's connection

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/e970722a-e0ad-44b5-a569-b8ddb2e70006" />

**Total time spent: 9h**



# August 7th: Assembling

Attached the handlebar pipe and twist throttle mount

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/740d7ede-5e2e-4cb1-9e28-cced015b86be" />

Attached the two middle wheels

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/b34675bc-a33c-4c0c-a7d4-9c0d77f55803" />

Fully bolted on the front fork and wheel. It took a while to keep everything aligned while attaching. It wasn't strong enough so I had to weld the pipes of the fork to the threaded rod.

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/661e0cfa-de9c-4649-ba3f-1698f597cf40" />

Attached the rear swing arm

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/c566babe-41b1-4ba7-97bf-6a987cd37590" />

Finished assembly:

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/66c4f18f-c92e-4f2e-9f8c-89cc067ebbe0" />
<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/340a79a6-a205-45ca-8667-6d1989cd006e" />

**Total time spent: 6h**



# August 10th: Electronics

I put the battery modules on the threaded rods and measured the distance between terminals. I marked the aluminum bars, drilled holes, then cut the bus bars off. I did the same for the long bars that carry power to the back. I bolted on the bars and tested their voltage. The entire battery pack was 48V. To make installation safer, I surrounded each long bar with cardboard, added a plastic bar between for support, and covered the rest of the terminals and bus bars with cardboard.

<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/73927d9f-eee1-4d3a-8fa4-2d6bb04238f6" />
<img width="579" height="769" alt="image" src="https://github.com/user-attachments/assets/e26b05b0-bbe5-4811-b098-9c93794dd04f" />

**Total time spent: 4.5h**



# August 11th: Electronics 2

I attached the hoverboard motor to a controller for testing. They're VESCs, so I downloaded VESC Tool and watched some tutorials on how to use it. I powered the controller and 

**Total time spent: 6h**
