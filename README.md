# Bike Rear-View Car Detector

A bike-mounted system that detects cars approaching from behind and warns the rider with an LED and buzzer.

A Raspberry Pi 5 with a rear-facing camera runs object detection and sends warnings over a CAN bus to an STM32 microcontroller, which controls the alerts. The two-board design follows how real vehicle electronics are built.

> This is an experimental prototype, not a certified safety device.

## Features

- Detects cars behind the bike using a camera and an object detection model
- Three warning levels: none, approaching, and close
- Pi 5 and STM32 communicate over CAN at 500 kbit/s
- Failsafe: the STM32 shows a fault light if it stops hearing from the Pi

## How It Works

1. The camera records the road behind the bike.
2. The Pi 5 detects cars and checks whether they are getting closer.
3. The Pi 5 sends the warning level to the STM32 over CAN.
4. The STM32 turns on the LED and buzzer based on the warning level.

## Hardware

- Raspberry Pi 5
- Raspberry Pi Camera Module
- MCP2515 CAN HAT for the Pi
- STM32 Nucleo-F446RE
- SN65HVD230 CAN transceiver
- LED and buzzer
- Power bank

## Software

- **Pi 5:** Python, OpenCV, Picamera2, python-can
- **STM32:** C, STM32 HAL, STM32CubeIDE

## Setup

### Raspberry Pi

```bash
git clone https://github.com/jaeak/bike-car-detector.git
cd bike-car-detector
pip install -r requirements.txt
```

### STM32

Open the `stm32/` folder in STM32CubeIDE, build the project, and flash it to the Nucleo board.

## Usage

Connect both boards to the CAN bus, power them on, and start the detector on the Pi:

```bash
python3 pi/main.py
```

## Project Structure

```text
bike-car-detector/
├── pi/       # Detection and CAN code (Python)
├── stm32/    # Alert firmware (C)
├── cad/      # SolidWorks mount files
└── docs/     # Notes and diagrams
```


## License

MIT
