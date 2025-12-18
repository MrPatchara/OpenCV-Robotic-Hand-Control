<div align="center">

# 🤖 OpenCV Robotic Hand Control

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.0+-green.svg)](https://opencv.org/)
[![ESP32](https://img.shields.io/badge/ESP32-Arduino-orange.svg)](https://www.espressif.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Control a robotic hand in real-time using hand gesture recognition with OpenCV and ESP32**

[Features](#-features) • [Demo](#-demo) • [Installation](#-installation) • [Usage](#-usage) • [Hardware](#-hardware) • [Contributing](#-contributing)

---

</div>

## 📖 Overview

This project enables real-time control of a robotic hand using computer vision and hand tracking. By leveraging OpenCV and MediaPipe's hand detection capabilities, the system tracks your hand gestures through a webcam and translates them into servo motor movements on a 3D-printed robotic hand controlled by an ESP32 microcontroller.

### 🎯 Key Features

- ✨ **Real-time Hand Tracking**: Detects and tracks hand gestures using OpenCV and CVZone
- 🎮 **Intuitive Control**: Natural hand movements control the robotic hand
- 🔌 **Serial Communication**: Seamless communication between Python application and ESP32
- 🎨 **Modern GUI**: Beautiful dark-themed interface with retro aesthetics
- 📊 **Live Feedback**: Real-time serial output display
- 🔧 **Easy Configuration**: Simple COM port selection for ESP32 connection
- 📐 **Circuit Diagram**: Built-in circuit diagram viewer

---

## 🎬 Demo

<div align="center">

### Watch the Demo Video

[![Robotic Hand Control Demo](https://img.youtube.com/vi/LW4NS92Rs7Y/0.jpg)](https://www.youtube.com/watch?v=LW4NS92Rs7Y)

**[Click here to watch on YouTube](https://www.youtube.com/watch?v=LW4NS92Rs7Y)**

</div>

---

## 🔌 Circuit Diagram

<div align="center">

### 📐 Complete Wiring Schematic

<a href="code_openCV/Picture1.png">
  <img src="code_openCV/Picture1.png" alt="Circuit Diagram" width="90%">
</a>

**ESP32 Robotic Hand Circuit Diagram**

*Click the image to view in full size. This diagram shows the complete wiring connections between ESP32, servo motors, and power supply.*

</div>

---

## 🚀 Features

### Hand Tracking System
- **Single Hand Detection**: Optimized for tracking one hand at a time
- **Finger Recognition**: Detects all 5 fingers (thumb, index, middle, ring, pinky)
- **Real-time Processing**: Low-latency gesture recognition
- **Visual Feedback**: Live camera feed with hand landmarks

### Robotic Hand Control
- **5 Servo Motors**: Independent control of each finger
- **Binary Control**: Each finger can be extended (180°) or retracted (0°)
- **Synchronized Movement**: Robotic hand mirrors your hand gestures

### User Interface
- **Fullscreen Mode**: Immersive experience when tracking
- **Dark Theme**: Eye-friendly dark interface with orange accents
- **Serial Monitor**: Real-time display of sent commands
- **Circuit Viewer**: Built-in circuit diagram reference

---

## 📋 Requirements

### Software
- Python 3.7 or higher
- OpenCV (`cv2`)
- CVZone (`cvzone`)
- Tkinter (usually included with Python)
- PIL/Pillow
- PySerial

### Hardware
- **ESP32 Development Board**
- **5x Servo Motors** (e.g., SG90 or similar)
- **Webcam** (USB camera or built-in)
- **3D-Printed Robotic Hand** (InMoov style)
- **USB Cable** (for ESP32 connection)
- **Power Supply** (for servos)

---

## 🔧 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/MrPatchara/OpenCV-RobotHand.git
cd OpenCV-RobotHand
```

### 2. Install Python Dependencies

```bash
pip install opencv-python
pip install cvzone
pip install pillow
pip install pyserial
```

Or install all at once:

```bash
pip install opencv-python cvzone pillow pyserial
```

### 3. Upload Arduino Code to ESP32

1. Open `Robot_inmoov.ino` in Arduino IDE
2. Install the **ESP32Servo** library
3. Select your ESP32 board and COM port
4. Upload the code to your ESP32

### 4. Hardware Setup

1. Connect servos to ESP32 pins:
   - Thumb → Pin 15
   - Index → Pin 16
   - Middle → Pin 17
   - Ring → Pin 18
   - Pinky → Pin 19
2. Connect ESP32 to your computer via USB
3. Ensure your webcam is connected and working

---

## 💻 Usage

### Running the Application

1. Navigate to the `code_openCV` directory:
   ```bash
   cd code_openCV
   ```

2. Run the main application:
   ```bash
   python v7.py
   ```

### Using the Interface

1. **Connect ESP32**:
   - Click `Settings` → `Select COM Port`
   - Choose your ESP32's COM port from the dropdown
   - Click `Save`

2. **Start Tracking**:
   - Click `Start Camera` button
   - Position your hand in front of the camera
   - The robotic hand will mirror your finger movements

3. **Stop Tracking**:
   - Click `Stop Camera` to stop the tracking
   - Click `Exit` to close the application

### Viewing Circuit Diagram

- Go to `Menu` → `Circuit Diagram` to view the wiring diagram

---

## 🔌 Hardware Configuration

### Circuit Diagram Reference

<div align="center">

![Circuit Diagram](code_openCV/Picture1.png)

*Refer to the detailed circuit diagram above for complete wiring instructions*

</div>

### ESP32 Pin Connections

| Finger | Servo Pin | ESP32 Pin |
|--------|-----------|-----------|
| Thumb  | Signal    | GPIO 15   |
| Index  | Signal    | GPIO 16   |
| Middle | Signal    | GPIO 17   |
| Ring   | Signal    | GPIO 18   |
| Pinky  | Signal    | GPIO 19   |

### Power Requirements

- **ESP32**: Powered via USB (5V)
- **Servos**: External power supply recommended (5V-6V, sufficient current for all servos)
- **Common Ground**: Ensure all components share a common ground

---

## 📁 Project Structure

```
OpenCV-RobotHand/
│
├── code_openCV/          # Main Python application
│   ├── v7.py            # Main application file
│   ├── v1.py - v6.py    # Previous versions
│   ├── circuit.png      # Circuit diagram icon
│   ├── com.png          # COM port icon
│   ├── icon.ico         # Application icon
│   ├── pic-title.png    # Title image
│   └── Picture1.png     # Circuit diagram
│
├── Robot_inmoov.ino     # ESP32 Arduino code
├── README.md            # This file
└── LICENSE              # MIT License
```

---

## 🛠️ Troubleshooting

### Camera Not Working
- Ensure your webcam is connected and not being used by another application
- Try changing the camera index in `v7.py` (line 163): `cv2.VideoCapture(1)` instead of `cv2.VideoCapture(0)`

### ESP32 Not Connecting
- Check if the correct COM port is selected
- Ensure ESP32 drivers are installed
- Try unplugging and reconnecting the ESP32
- Verify the baud rate is set to 115200

### Servos Not Moving
- Check power supply connections
- Verify servo connections to correct GPIO pins
- Ensure servos are receiving adequate power
- Check serial communication in the Serial Monitor

### Hand Not Detected
- Ensure good lighting conditions
- Keep hand clearly visible in camera frame
- Try adjusting `detectionCon` parameter in `v7.py` (line 15)

---

## 🎨 Customization

### Adjusting Detection Sensitivity

In `v7.py`, modify the detection confidence:

```python
self.detector = HandDetector(maxHands=1, detectionCon=0.7)  # Change 0.7 to adjust sensitivity
```

### Changing Servo Angles

In `Robot_inmoov.ino`, modify the servo positions:

```cpp
servoThumb.write(180);  // Extended position
servoThumb.write(0);    // Retracted position
```

### Customizing GUI Theme

Modify the color scheme in `v7.py` (lines 19-25):

```python
self.bg_color = "#1a1a1a"      # Background color
self.fg_color = "#ff6600"      # Text color
self.button_bg = "#3e4a4f"     # Button background
```

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Developer

**Patchara Al-umaree**

- 📧 Email: [Patcharaalumaree@gmail.com](mailto:Patcharaalumaree@gmail.com)
- 📱 Phone: +66 96 061 4238
- 🔗 GitHub: [@MrPatchara](https://github.com/MrPatchara)

---

## 🙏 Acknowledgments

- **CVZone** - For the excellent hand tracking module
- **OpenCV** - For computer vision capabilities
- **MediaPipe** - For hand landmark detection
- **ESP32 Community** - For hardware support and resources
- **InMoov Project** - For robotic hand design inspiration

---

## ⚠️ Disclaimer

**This project is for educational and personal use only. Not intended for commercial use.**

---

<div align="center">

### ⭐ If you find this project helpful, please consider giving it a star!

Made with ❤️ by [Patchara Al-umaree](https://github.com/MrPatchara)

</div>
