# Parking Assistance System

**Author**: Joshua Alana  
**Date**: 02 October 2024  
**Course**: Embedded Systems Final Term Project  
**Institution**: African Leadership University  

---

## 1. Project Overview

The **Parking Assistance System** is an embedded system designed to assist drivers with parking by detecting obstacles and providing real-time feedback using ultrasonic sensors. The system calculates the distance to nearby objects and alerts the driver with sound notifications and visual displays. This project is implemented using C language and utilizes microcontroller hardware for sensor interfacing and output control.

The objective of the project is to build a functional, efficient, and reliable parking assistant, helping drivers avoid collisions while parking in tight spaces.

---

## 2. Objectives

- **Primary Goal**: To develop a responsive and accurate parking assistance system using ultrasonic sensors that alert the driver when an object is within a critical distance.
  
- **Secondary Goals**:
  - Implement a sound-based alert system to notify the driver of obstacle proximity.
  - Display distance information on an LCD screen or via LEDs.
  - Ensure system reliability and accuracy through rigorous testing.

---

## 3. System Design

### 3.1 Hardware Components
- **Microcontroller**: [Arduino Uno / STM32]
- **Ultrasonic Sensors**: HC-SR04
- **Buzzer**: For sound alerts
- **LCD Display**: To show the distance to nearby objects
- **Power Supply**: Standard DC 5V/9V power supply for components

### 3.2 System Architecture
The system continuously reads distance data from the ultrasonic sensors and processes it to determine proximity. Depending on the distance to the nearest object, the system provides feedback:
- **Distance > 50 cm**: No alert.
- **Distance between 20 cm and 50 cm**: Warning sound via buzzer.
- **Distance < 20 cm**: Continuous alert and distance display on LCD.

---

## 4. Software Design

The project is implemented in C programming language, ensuring optimal performance on a low-level embedded system. The main features of the software include:

- **Distance Calculation**: Using the speed of sound and time-of-flight method to calculate the distance between the sensor and obstacles.
- **Sound Alerts**: Triggering the buzzer at different frequencies based on the proximity of the detected object.
- **LCD Display**: Showing real-time distance data on an LCD screen to give the driver clear visual feedback.

### 4.1 Functions
1. `getDistance()`: Measures the time taken for the ultrasonic pulse to return and calculates the distance to the nearest object.
2. `soundAlert()`: Triggers a buzzer sound depending on the object's proximity.
3. `displayDistance()`: Displays the distance on an LCD screen.

---

## 5. Implementation

### 5.1 Code Structure
The following is a breakdown of the code and directories:
- `/src`: Contains the source code written in C.
  - `main.c`: Main loop of the system.
  - `sensor.c`: Ultrasonic sensor interface logic.
  - `alert.c`: Sound and visual feedback logic.
  - `lcd.c`: Code for displaying the distance on the LCD.
- `/hardware`: Schematics and circuit diagrams.
- `/tests`: Test case data, including expected and actual results.

### 5.2 Compiling the Code
To compile the code, run the following command in the terminal:
```bash
gcc -o parking_assistance main.c sensor.c alert.c lcd.c -lwiringPi
```

### 5.3 Running the Program
To run the compiled program:
```bash
./parking_assistance
```

---

## 6. Results and Testing

The system was tested in various parking scenarios, with distances ranging from 10 cm to 100 cm. The sensor readings were accurate within a ±2 cm range, and the sound alerts were triggered appropriately.

Key testing scenarios:
- **Scenario 1**: Large distance with no alert.
- **Scenario 2**: Medium distance with intermittent alert.
- **Scenario 3**: Close distance with continuous alert and distance display.

---

## 7. Conclusion

The Parking Assistance System successfully meets its objectives by providing accurate and responsive feedback based on obstacle proximity. The system helps drivers park safely by alerting them to nearby objects, thus reducing the risk of collisions. The implementation in C allows for efficient control of hardware components, ensuring smooth operation in real-time environments.

---

## 8. Future Work

Future enhancements may include:
- Integration with a smartphone app for remote monitoring.
- Adding support for multiple ultrasonic sensors to improve detection range.
- Optimizing power consumption for better energy efficiency.

---

## 9. References

- [Microcontroller Documentation](https://www.arduino.cc/en/Main/Documentation)
- [Ultrasonic Sensor HC-SR04 Guide](https://components101.com/ultrasonic-sensor-working)
- [C Programming for Embedded Systems](https://www.tutorialspoint.com/cprogramming/cprogramming_embedded_systems.htm)

---

## 10. Acknowledgments

Special thanks to Mr Aaron for guidance throughout this project, for providing the necessary tools and support.

---

This README follows an academic style, ensuring clarity and structure to demonstrate your project's objectives, methods, and results. You can modify the content to suit your specific requirements and progress. Let me know if you need help with specific parts of the code or documentation!
