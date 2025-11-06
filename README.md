# GPT-30X
Transform a TI-30X IIS into the ultimete cheating device, using a RasperryPi Zero 2 W.

**GPT-30X** is a modified **TI-30X IIS** calculator powered by a **Raspberry Pi Zero 2 W**.  
It replaces the calculator’s original internals with a miniature Linux system capable of running **ChatGPT over Wi-Fi**, fully controlled via the calculator’s original key matrix.

> A retro-tech fusion of classic design and modern AI intelligence.

---

## Features

- ChatGPT integration over Wi-Fi using OpenAI or OpenRouter API  
- Full key matrix input using the original TI-30X IIS keyboard  
- Dual-mode system  
  - AI Chat Mode – talk to ChatGPT directly from your calculator  
  - Calculator Mode – switch back to normal math mode instantly  
- Emergency button to exit ChatGPT mode and return to calculator mode  
- Compact display matching the original LCD footprint  
- Low-power Pi Zero 2 W setup, boots directly into ChatGPT without menus  

---

## Hardware Overview

| Component | Description |
|------------|-------------|
| Mainboard | Raspberry Pi Zero 2 W |
| Display | Small SPI TFT display (same size as original LCD) |
| Keyboard PCB | Custom-made matrix PCB matching TI-30X IIS layout |
| Emergency Button | Physical GPIO button to switch modes instantly |
| Wi-Fi | Built-in (no SIM or cellular connection) |
| Power | Internal Li-ion battery or USB input |

---

## Software Architecture

/home/pi/gpt30x/
│
├── main.py # Main control loop (mode switching)
├── chatgpt_mode.py # Online ChatGPT client logic
├── calc_mode.py # Offline calculator logic
├── keyboard.py # GPIO matrix handling
├── display.py # Display rendering and text handling
└── emergency_button.py # Interrupt-based mode switch


### Boot Behavior

- On power-up, GPT-30X automatically connects to Wi-Fi  
- Launches `main.py` directly (no desktop)  
- Starts in ChatGPT Mode  
- Pressing the Emergency Button toggles between ChatGPT and Calculator modes  

---

## Quick Start (WIP)

1. Flash **Raspberry Pi OS Lite** to your SD card  
2. Copy this repository to `/home/pi/gpt30x/`  
3. Install dependencies:
   ```bash
   sudo apt update
   sudo apt install python3-pip python3-rpi.gpio
   pip install openai
   ```
   
