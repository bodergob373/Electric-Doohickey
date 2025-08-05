# Electric-Doohickey

**NOTE:**  Due to safety concerns, the wiring and components have changed. New BOM: https://docs.google.com/spreadsheets/d/1_RJHmHq7QkmXvIXKIsm6De2D1rjghpJohdq1jAkP7gE/edit?usp=sharing

## New Description
A custom go-kart powered by 6 Nissan Leaf battery modules. It is driven by two hoverboard motors. The throttle sends signals to a microcontroller, which sends adjusted signals to both motor controllers. The rear wheels are on a suspension arm 

## Description (OLD)
A BMS with an array of 20 2nd-Gen Nissan Leaf battery modules in a 10s2p configuration connected to a motor controller and a 12kW 72V hub motor all placed in a small custom go-kart. The wheels are in a diamond configuration with one steerable wheel, one powered rear wheel, and two stabilizing wheels.

## Why?
My main goal for the future is to build an ethanol-electric hybrid car from scratch. To do this, I need real-world experience designing electrical and mechanical stuff and more practice welding. I'm making this project so that I can design the electric part of the hybrid car and test it on a small, fast, and fun vehicle with only half the number of batteries, motor controllers, and motors.

## New Model
<img width="610" height="424" alt="image" src="https://github.com/user-attachments/assets/f6b0e238-7900-4056-a866-e5787b8628e1" />
<img width="966" height="529" alt="Screenshot 2025-08-04 184146" src="https://github.com/user-attachments/assets/e4291918-c3bc-44a8-8764-46a8a9be561d" />
<img width="552" height="395" alt="Screenshot 2025-08-04 184208" src="https://github.com/user-attachments/assets/193a126a-9406-4f8c-9a86-e15e52bb1972" />

## New Wiring Diagram
<img width="1011" height="613" alt="Screenshot 2025-08-02 141453" src="https://github.com/user-attachments/assets/ad0adb3f-e657-458c-b300-bd0474579821" />


### 3D Printed Parts for Mounting the Twist Throttle and Hoverboard Motor (models were updated)
<img width="814" height="633" alt="Screenshot 2025-07-12 105221" src="https://github.com/user-attachments/assets/3852722a-2500-45fb-8667-b3d0ac19703d" />

### Hoverboard Motor Connected with 3D-Printed Mount
<img width="1180" height="641" alt="Screenshot 2025-07-12 105755" src="https://github.com/user-attachments/assets/8329be57-ad78-4524-af9e-ba135a3b3dfd" />

### New BOM:

| Part                                   | Purpose                                     | Amount    | Cost   |
|----------------------------------------|---------------------------------------------|-----------|--------|
| Curved and straight metal tubes        | Frame                                       | 4 curved, 6 straight | $0.00  |
| Extension springs                      | Rear suspension                             | 4         | $0.00  |
| Plastic chair                          | Seat                                        | 1         | $0.00  |
| 10" tires                              | Front wheel and stabilizers                  | 3         | $0.00  |
| Hoverboard motor                       | Rear wheels                                 | 2         | $0.00  |
| ESP32                                  | Send throttle input to both controllers     | 1         | $0.00  |
| 2S LiPo battery                        | Power microcontroller and contactor         | 1         | $0.00  |
| Switch                                 | Connect small battery to microcontroller and contactor | 1         | $0.00  |
| 3/4" x 24" threaded rod                | Hold suspension arm                         | 1         | $10.51 |
| 5/16" x 72" threaded rod               | Hold battery modules                        | 1         | $7.57  |
| 5/8" x 12" threaded rod                | Hold front wheel and springs                | 1         | $4.34  |
| 5/8" x 36" threaded rod                | Axle for stabilizing wheels                 | 1         | $11.31 |
| 1/2" x 36" threaded rod                | Steering rod                                | 1         | $7.93  |
| Used 2nd-gen Nissan Leaf battery modules | Power motors                               | 6         | $80.00 |
| Twist throttle                         | Throttle                                    | 1         | $4.94  |
| Motor controllers                      | Control motors                              | 2         | $120.00|
| 135A contactor                         | Connect battery to motor controllers when turned on | 1         | $14.29 |
| 0.25" x 1" x 72" aluminum flat bar     | Bus-bars for battery power terminals        | 2         | $18.72 |
| 20mm M6 bolts                          | Connect power terminals to bus-bars         | 30        | $8.07  |
| 100 ft 20 AWG silicone wire            | Connect to throttle and contactor           | 100 ft    | $13.98 |
| 1/4" ring terminals                    | Connect to throttle and contactor           | 100       | $8.99  |
| 20 ft 8 AWG silicone wire              | Connect motor controller to battery and motors | 20 ft   | $19.99 |
| 1/2" shaft collars                     | Hold parts on steering rod                  | 10        | $8.49  |
| 5/8" shaft collars                     | Hold wheel nuts in place                    | 10        | $8.49  |
| 3/4" shaft collars                     | Hold suspension arm in place                | 8         | $13.99 |
| Misc screws, nuts, and washers         | Attach wheels, springs, steering, throttle  | ~20       | $10.00 |
|                                        | **Total**                                   |           | **$371.61** |

## The Model (OLD)
<img width="1355" height="663" alt="Screenshot 2025-07-12 110322" src="https://github.com/user-attachments/assets/b19d8a25-2438-4d9c-b7cc-8efc292bb08f" />

### Electrical Components, Rear Suspension Arm, Hub Motor, and Trampoline Springs (OLD)
<img width="1222" height="713" alt="Screenshot 2025-07-12 113456" src="https://github.com/user-attachments/assets/f69f9b54-0b67-4e2d-8d7e-9906c24720a9" />

### Wiring Between the Battery Modules, BMS, Motor Controller, Motor, Throttle, Relays, and Pre-Charge Resistor (OLD)
<img width="1011" height="483" alt="Screenshot 2025-07-12 114216" src="https://github.com/user-attachments/assets/07e117c6-9ec7-4bad-ba7d-b07f94e42e12" />

### Actual Wiring Diagram (OLD)
<img width="1251" height="718" alt="Screenshot 2025-07-17 142454" src="https://github.com/user-attachments/assets/3e0026eb-d149-4a3d-b5ab-d5b6e3278a23" />

### How it's Gonna Look (OLD)
<img width="1078" height="610" alt="Screenshot 2025-07-12 113755" src="https://github.com/user-attachments/assets/6d4620c8-9413-4e66-97b8-09daae57c3c4" />

## BOM (OLD):
https://docs.google.com/spreadsheets/d/1RJjejwJ8y24ydcLwPVteclJ-zP17mWSHqXySRraKmQs/edit?usp=sharing
