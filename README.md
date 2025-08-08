# SONAR-using-arduino
Arduino SONAR Project with Processing Visualization
This repository contains the code and documentation for a low-cost, real-time SONAR (Sound Navigation and Ranging) system built with an Arduino Uno. The project uses an ultrasonic sensor mounted on a servo motor to scan a 180-degree area, detect objects, and visualize them on a radar-like display created with the Processing language.

Core Features

180-Degree Scanning: A servo motor sweeps an ultrasonic sensor to cover a wide field of view.
Real-Time Object Detection: Uses an HC-SR04 ultrasonic sensor to measure distances based on time-of-flight.
Live Data Visualization: A custom-built GUI in Processing displays the scanned area as a radar screen, showing detected objects and clear paths in real-time.
Serial Communication: The Arduino sends angle and distance data to the Processing application over a serial connection.
Cost-Effective & Accessible: Built entirely with common, low-cost components, making it ideal for educational purposes, robotics, and hobbyist projects.

Hardware & Software
Hardware Components
Microcontroller: Arduino Uno
Sensor: HC-SR04 Ultrasonic Distance Sensor
Actuator: SG90 Micro Servo Motor
Prototyping: Breadboard and Jumper Wires
Power: 5V DC Power Source (via USB)
Software & Tools
IDE: Arduino IDE
Visualization: Processing IDE
Programming Languages: C/C++ (for Arduino), Java (for Processing)

How It Works

The system operates in a continuous loop, integrating hardware control and software visualization.
Servo Sweep: The Arduino code commands the SG90 servo to move in 1-degree increments, sweeping from 0 to 180 degrees and back.
Distance Measurement: At each angle, the Arduino triggers the HC-SR04 sensor. It sends out an ultrasonic pulse and measures the time it takes for the echo to return.
Calculation: The measured time is converted into distance (in centimeters) using the speed of sound.
Data Transmission: The Arduino formats the current angle and the measured distance into a string (e.g., "90,35") and sends it over the USB serial port.
Visualization: The Processing application continuously listens for this serial data. It parses the angle and distance, converts these polar coordinates to Cartesian (x, y) points, and draws them on the radar display. Detected objects are typically shown in red, while clear areas are traced in green.

Setup & Installation

To get this project running, you will need to program both the Arduino and run the visualization sketch in Processing.
Clone the Repository:
Program the Arduino:
Open the .ino file in the Arduino IDE.
Connect your Arduino Uno to your computer.
Select the correct board (Arduino Uno) and COM port from the Tools menu.
Upload the sketch to the Arduino.
Run the Processing GUI:
Open the .pde file in the Processing IDE.
Important: Make sure the COM port listed in the Processing sketch matches the one your Arduino is connected to. You may need to edit this line in the code: myPort = new Serial(this, Serial.list()[x], 9600); (where x is the index of your Arduino's port).
Run the sketch. The radar display should appear and start visualizing the data from the Arduino.

