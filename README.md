# STM_Traffic_Light

A precision traffic light controller application designed for embedded systems. This project utilizes the **STM32F446RE** microcontroller (ARM Cortex-M4) to simulate and manage a synchronized traffic intersection sequence using GPIO configurations and timing controls.

---

## 🛠️ Hardware & Architecture Details
* **Microcontroller:** STM32F446RET6 (LQFP64)
* **Core:** ARM Cortex-M4 with FPU @ 180 MHz
* **Development Environment:** STM32CubeIDE (v1.16.0)
* **Configuration Tool:** STM32CubeMX (Integrated `.ioc` configuration)
* **Programming Language:** C

---

## 🚀 Project Structure

The repository contains the standard STM32CubeIDE project structure:
* **`Core/`**: Contains the main application logic (`Src/main.c`), system initializations, and interrupt vectors.
* **`Drivers/`**: STM32F4xx HAL (Hardware Abstraction Layer) and CMSIS libraries.
* **`traffic_light.ioc`**: The hardware configuration file for pin mapping, clock trees, and peripherals.
* **`STM32F446RETX_FLASH.ld`**: Linker script allocating code sections to Flash memory.

---

## 🚦 Features & Logic Flow

The controller manages state-based sequencing to emulate real-world traffic intersections:
1. **Normal Sequence:** Cycles through standard Green 🟢 -> Yellow 🟡 -> Red 🔴 states using non-blocking delays or hardware timers.
2. **Hardware Abstraction:** Built on the STM32 HAL framework for reliable GPIO pin manipulation (`HAL_GPIO_WritePin` / `HAL_GPIO_TogglePin`).
3. **Modular Codebase:** Clean separation between the auto-generated hardware initialization layer and user-defined state machine logic.

---

## 💻 How to Run Locally

### Prerequisites
1. Install [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html).
2. Connect your **ST-LINK V2** debugger (built into the NUCLEO-F446RE board) to your computer.

### Setup Instructions
1. **Clone the repository using your SSH key:**
   ```bash
   git clone git@github.com:NANDAVELAN/STM_Traffic_Light.git
