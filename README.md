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
✧ Flame Detection: Three IR flame sensors (left, center, and right) for directional intensity comparison<br/>
✧ Autonomous Navigation: Four-wheel differential drive with independent motor control via L298N<br/>
✧ Fire Suppression: TIP-122 transistor-driven water pump with servo-controlled spray mechanism<br/>
✧ Auditory Feedback: Speaker alerts signal for both detection and extinguishing events<br/>
✧ Battery Powered: Two 3.7V batteries provide sufficient current for motors and pump

## Hardware

### Core Components
✧ STM32 Nucleo-F401RE microcontroller<br/>
✧ 3 IR flame sensors (analog detection, A0–A2 pins)<br/>
✧ 4 DC gear motors + L298N motor driver<br/>
✧ Water pump with TIP-122 transistor, 1N4007 diode, and smoothing capacitors<br/>
✧ Servo motor for sweeping spray motion<br/>
✧ Piezo speaker for real-time feedback<br/>
✧ 2 3.7V Li-ion batteries<br/>

### Block Diagram

### Circuit Diagram

## Proccess

## Results 

## Demo
