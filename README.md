# Sign Glove Project


# Overview

The Sign Glove is an innovative wearable device designed to assist in communication, particularly for the deaf and hard-of-hearing community. This glove translates finger gestures into pre-recorded audio outputs. By bending individual fingers, the glove triggers specific sounds or words via an integrated speaker, enabling simple sign language interpretation in real-time. Built using affordable Arduino components, this project is perfect for makers, educators, and accessibility enthusiasts looking to explore IoT and assistive technology.

This repository contains the complete Arduino code, wiring diagrams, and build instructions to replicate or extend the project.

## Features

- **Gesture Detection:** Each of the five fingers is equipped with a flex sensor to detect bending movements.
- **Audio Playback:** Pre-built sounds or words are played through the speaker when a finger is bent, with each finger mapped to a unique audio file.
- **Portable Design:** Powered by a 5V battery, making it lightweight and wearable.
- **Customizable:** Easily modify audio files or add more complex gestures by editing the code.
- **Real-Time Response:** Low-latency detection and playback for seamless user experience.

## Components Required

- **Arduino Nano:** The microcontroller brain of the project.
- **DFPlayer Mini:** MP3 module for handling audio playback.
- **Speaker:** Small speaker for audio output (e.g., 8Ω, 0.5W).
- **Protoboard:** For prototyping and soldering the circuit.
- **5 Flex Sensors:** One for each finger to detect bends (typically 2.2" or similar size).
- **5V Battery:** Rechargeable or standard battery pack for portability.
- Additional: Jumper wires, resistors (if needed for sensors), a glove (for mounting), and basic soldering tools.

## Wiring Diagram

available above

For a detailed schematic:
- Flex Sensors: Connected to analog pins A0-A4 on Arduino Nano, with voltage dividers (10kΩ resistors recommended).
- DFPlayer Mini: RX to D10, TX to D11, VCC/GND to 5V/GND, Speaker to SPK1/SPK2.
- Speaker: Directly to DFPlayer.
- Battery: Powers the entire setup via Arduino's VIN/GND.


## Installation and Setup

1. **Hardware Assembly:**
   - Mount the flex sensors on the fingers of a glove using tape or sewing.
   - Solder components on the protoboard as per the wiring diagram.
   - Connect the Arduino Nano and upload the code.

2. **Software Setup:**
   - Install the Arduino IDE from [arduino.cc](https://www.arduino.cc/en/software).
   - Install required libraries:
     - `DFRobotDFPlayerMini` (for DFPlayer).
     - No additional libraries needed for flex sensors (analog reads).
  

3. **Audio Files:**
   - Prepare MP3 files for each finger (e.g., "thumb.mp3", "index.mp3", etc.).
   - Copy them to a microSD card and insert into the DFPlayer Mini.
   - Map file numbers in the code (e.g., file 1 for thumb, file 2 for index).

4. **Upload Code:**
   - Connect Arduino Nano via USB.
   - Select the correct board and port in Arduino IDE.
   - Upload the sketch.

## Usage

1. Wear the glove and power it on.
2. Bend a finger: The corresponding flex sensor detects the change in resistance.
3. The Arduino processes the input and triggers the DFPlayer to play the assigned audio file through the speaker.
4. Example: Bending the thumb might play "Hello", index "Yes", etc. Customize as needed!

For calibration:
- Adjust threshold values in the code (`flexThreshold`) based on your sensors' resistance range.

## Code Structure

- `sign_glove.ino`: Main Arduino sketch.
  - Setup: Initializes pins, DFPlayer, and serial communication.
  - Loop: Reads flex sensor values, checks for bends, and plays audio if threshold met.
- `docs/`: Contains wiring diagrams and additional notes.


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by assistive tech communities and open-source Arduino projects.
- Thanks to the team for collaboration!

If you build this, share your version or feedback in the issues section. Let's make tech more inclusive! 🚀
