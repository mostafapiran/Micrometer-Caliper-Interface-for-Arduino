# Micrometer-Caliper-Interface-for-Arduino

<p align="center">
 <img src="https://github.com/mostafapiran/Micrometer-Caliper-Interface-for-Arduino/blob/main/2.jpg">
</p>

## Overview

This GitHub repository contains an Arduino project that serves as an interface between an Arduino board and a micrometer caliper through a serial connection. The code enables communication with the micrometer, allowing the Arduino to retrieve and interpret measurement data. This ReadMe provides a detailed explanation of the project's key components.

## Hardware Setup

The micrometer's communication involves three lines connected to specific Arduino pins:
- **REQ (Request):** Connected to Arduino pin 5.
- **DAT (Data):** Connected to Arduino pin 2.
- **CLK (Clock):** Connected to Arduino pin 3.

<p align="center">
 <img src="https://github.com/mostafapiran/Micrometer-Caliper-Interface-for-Arduino/blob/main/1.png">
 <img src="https://github.com/mostafapiran/Micrometer-Caliper-Interface-for-Arduino/blob/main/3.png">
</p>

The setup() function initializes these pins using pinMode and sets the initial state of the REQ line with `digitalWrite(req, LOW)`.

## Serial Communication

Serial communication is established with the Serial library at a baud rate of 9600 (`Serial.begin(9600)`). This allows the Arduino to communicate with an external device, typically a computer, through the serial port.

## Data Acquisition and Parsing

The loop() function is responsible for retrieving data from the micrometer. It generates a request signal (`digitalWrite(req, HIGH)`) and reads the data bits from the DAT line based on the clock signal from the CLK line. The received data is stored in the `mydata` array.

The code interprets the data, extracting information such as sign, value, decimal position, and units. The measurement information is then converted into a human-readable format.

## Output Handling

The interpreted measurement value is printed to the serial monitor, considering the sign, value, and decimal precision. The code supports both positive and negative measurements.

## Usage

1. Connect the micrometer's REQ, DAT, and CLK lines to the specified Arduino pins.
2. Upload the provided code to the Arduino using the Arduino IDE.
3. Open the serial monitor to observe the interpreted measurement values.

## Customization

Users can customize the code to adapt it to specific micrometer models or communication protocols. Additionally, adjustments to the code can be made to match the baud rate of the micrometer.

## Contributions

Contributions and improvements are encouraged. If you encounter issues or have suggestions for enhancements, feel free to open an issue or submit a pull request.

This project aims to provide a flexible and functional interface between an Arduino board and a micrometer caliper, making it accessible for various applications and configurations.
 
