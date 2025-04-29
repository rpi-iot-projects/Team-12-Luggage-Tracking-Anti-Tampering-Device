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
- [OpenSSL](https://github.com/openssl/openssl)

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


## Usage

Instructions for setting up B.A.T.M.A.N Ad Hoc networks on a Raspberry Pi can be found inside the setup-batman.sh script in the root directory. This is essential for multiple devices to operate in a single mesh network

The mosquitto service needs to be enabled on a Raspberry Pi acting as an MQTT broker. It also needs to have an additional line in the file /etc/mosquitto.conf that says "allow_anonymous_connections FALSE" to ensure the network is TLS encrypted.

Lastly, the server (windows computer) needs to have a static IP pinned down on the ethernet port. It then needs to run 3 scripts:
1. /full_internet_server_code/app.js
2. /airport_server_code/server_main.py
3. /user_code/GUI.py

While the GUI works on other devices (such as mobile devices) due to HTTPS support, the GUI file needs to be running on the server for this connection to work. A request to the server's public IPv4 is also required for this interface to work on other devices.

## Results and Demonstration

With the default configuration for the Wi-Fi transciever on the Raspberry Pi 3B+, our team found a range of at least 40ft with a 3 device multi-hop. That range could be greatly expanded if a more powerful antenna was installed.

A live demo of this project can be found [HERE](https://youtu.be/4kCJANxVGjQ)
