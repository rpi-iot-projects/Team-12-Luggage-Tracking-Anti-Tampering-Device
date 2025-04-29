# IOT_Suitcase_Project

This project provides software used for creating IOT-enabled suitcases using a wifi mesh network between suitcases.  This project also provides the full solution for sending the data to a server which can be hosted for clients to access. 


## Table of Contents

- [Overview](#overview)  
- [Hardware Components](#hardware-components)  
- [Software and Dependencies](#software-and-dependencies)  
- [Usage](#usage)  
- [Results and Demonstration](#results-and-demonstration)  


## Overview

This project aims to develop an open-source Internet of Things (IoT) system for advanced luggage monitoring, addressing the problem of lost, stolen, or mishandled luggage encountered more and more frequently during travel. Unlike existing closed-source solutions like AirTag and Tile, this system provides a more transparent framework, potentially to setup software to aide both travelers and authorities like the TSA. Key features include Raspberry Pi-based clients embedded in luggage equipped with sensors (Camera, MPU6050 IMU, GPS, Reed Switch), a B.A.T.M.A.N. Advanced wireless mesh network enabling communication between clients without traditional infrastructure, MQTT protocol for data transmission over the mesh, a central Node.js server for data aggregation, and a Python/PyQt5 desktop application for users to monitor suitcase status, view images, and track events. 

## Hardware Components

- Raspberry Pi 3B+
- Intertial Measurement Unit (MPU 6050)
- Raspberry Pi Camera Module 2
- GPS (with NEO-6M module)
- Magnetic Reed Switch (3 wire)


## Software and Dependencies
 Software Packages:
- [Batman-adv](https://git.open-mesh.org/batman-adv.git)
- [Mosquitto](https://mosquitto.org/)
- [Node.js](https://github.com/nodejs/node)
- [Python 3.13](https://www.python.org/downloads/release/python-3133/)

PIP (Python) Packages:
- [DateTime](https://pypi.org/project/DateTime/)
- [PyQt5](https://pypi.org/project/PyQt5/)
- [paho-mqtt](https://pypi.org/project/paho-mqtt/)
- [picamera2](https://pypi.org/project/picamera2/)
- [RPi.GPIO](https://pypi.org/project/RPi.GPIO/)
- [mpu6050-PI](https://pypi.org/project/mpu6050-PI/)

NPM (Node.js) Packages:
- [express](https://www.npmjs.com/package/express)
- [express-session](https://www.npmjs.com/package/express-session)
- [bcrypt](https://www.npmjs.com/package/bcrypt)
- [readline](https://www.npmjs.com/package/readline)
- [path](https://www.npmjs.com/package/path)
- [https](https://www.npmjs.com/package/https)
- [ndjson](https://www.npmjs.com/package/ndjson)

