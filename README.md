# FlameBot - Autonomous Fire-Fighting Robot
An STM32-based autonomous robot for flame detection, navigation, and suppression

## Table of Contents
* [Introduction](#introduction)
* [Features](#features)
* [Hardware](#hardware)
* [Proccess](#process)
* [Results](#results)
* [Demo](#demo)

## Introduction
FlameBot was developed as a final project for my Embedded Systems course with the goal of building a robot capable of autonomously detecting and extinguishing small open flames. Inspired by existing Arduino-based fire-fighting robots, we aimed to push the design further by using an STM32 Nucleo-F401RE and incorporating auditory feedback for flame detection and suppression.

The project demonstrates how embedded systems knowledge, including digital/analog I/O, PWM, and transistor-based power control, can be applied to address real-world safety challenges.
	
## Features
✧ Flame Detection: Three IR flame sensors (left, middle, and right) for directional intensity comparison<br/>
✧ Autonomous Navigation: Four-wheel differential drive with independent motor control via L298N<br/>
✧ Fire Suppression: TIP-122 transistor-driven water pump with servo-controlled spray mechanism<br/>
✧ Auditory Feedback: Speaker alerts signal for both detection and extinguishing events<br/>
✧ Battery Powered: Two 3.7V batteries provide sufficient current for motors and pump

## Hardware

### Components
✧ Chassis frame + 4 wheels for solid base<br/>
✧ STM32 Nucleo-F401RE microcontroller<br/>
✧ 3 4-pin IR flame sensors (analog detection, A0–A2 pins)<br/>
✧ 4 DC gear motors + L298N motor driver<br/>
✧ Submersible water pump + pipe + plastic bottle for extinguishing system<br/> 
✧ Servo motor(SQ90) for sweeping spray motion<br/>
✧ Piezo speaker for real-time feedback<br/>
✧ TIP-122 transistor + 3 33 pf capacitators + 1kΩ resistor + 1N4007 diode<br/>
✧ Rocker Switch<br/>
✧ 2 3.7V Li-ion batteries<br/>
✧ Mini breadboard + jumper wires<br/>

### Block Diagram
<img width="538" height="385" alt="Screenshot 2025-08-27 at 6 07 58 PM" src="https://github.com/user-attachments/assets/009450a0-1954-478a-a684-220a7d312e1c" /><br/>
### Top Level Flow Chart
<img width="516" height="663" alt="Screenshot 2025-08-27 at 6 08 28 PM" src="https://github.com/user-attachments/assets/1f70d546-e1c1-4928-9e16-d883f77c32de" /><br/>
### Circuit Diagram
<img width="573" height="442" alt="Screenshot 2025-08-27 at 6 08 59 PM" src="https://github.com/user-attachments/assets/b82ee6ad-f9ad-4843-a834-4de89447aca4" /><br/>

## Proccess
### Design & Planning
Divided into subsystems:<br/>
✧ Part 1: Chassis & mobility (motors, sensors)<br/> 
✧ Part 2: Water pump & feedback system<br/> 
Used modular approach for easier debugging and integration<br/>

### Hardware Implementation
✧ Motors tested sequentially via L298N to validate wiring and current draw<br/>
✧ Flame sensors calibrated using potentiometer sensitivity tuning<br/>
✧ Water pump integrated with TIP-122 + diode protection to handle inductive kickback<br/>
✧ Servo calibrated for 0–180° sweep using PWM<br/>

### Software Implementation
Implemented using Mbed OS (C++)<br/>

Key control logic:<br/>
✧ Continuously read flame sensor analog values<br/>
✧ Compare sensor readings → determine flame direction<br/>
✧ Adjust wheel speeds using PWM for navigationg<br/>
✧ Trigger water pump + servo sweep when close to flame<br/>
✧ Play audio tones for detection/extinguish events<br/>

### Challenges Faced
✧  Power distribution: initially overheated Nucleo by incorrectly powering via 5V instead of VIN<br/>
✧  Pump reliability: weak tubing layout reduced water pressure, later fixed by repositioning<br/>
✧  Sensor limitations: IR sensors became ineffective outdoors due to sunlight interference<br/>
✧  Debugging: PyOCD deploy error traced back to Nucleo JP5 jumper configuration<br/>


## Results 
✧ Robot successfully detected flame direction, navigated toward it, and extinguished with water pump + servo sweep<br/>
✧ Speaker provided clear feedback on flame detection and extinguishing<br/>
✧ Limitations: outdoor performance degraded due to IR interference; pump reliability depended on correct diode and tubing setup<br/>

## Demo
* [Video Demonstation](https://www.youtube.com/watch?v=8UgjaaqpgME)



