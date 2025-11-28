# STM32-Blinky-HAL-on-Blue-Pill
A minimal STM32F103C8T6 (Blue Pill) project demonstrating how to toggle the onboard LED using the STM32 HAL library. This example shows the basic project structure generated with STM32CubeMX, GPIO configuration, and a simple main loop for beginners learning STM32 development.

A complete example project demonstrating how to toggle the onboard LED on the **STM32F103C8T6 (Blue Pill)** board using the **STM32 HAL** library. This project is ideal for beginners learning STM32 development, HAL drivers, and STM32CubeMX project structure.

---

## 📌 Overview

This repository contains a minimal STM32 project generated with **STM32CubeMX**, showing:

* Basic GPIO configuration using HAL
* Toggling the onboard LED (PC13)
* Main loop execution using HAL functions

This is a clean and simple reference project for starting STM32 development.

---

## 🛠 Requirements

To build and flash the project, you need:

* **STM32F103C8T6 (Blue Pill)** board
* **STM32CubeMX** (project generation)
* One of the following IDEs:

  * **Keil uVision 5**
  * **STM32CubeIDE**
  * **VS Code + ARM GCC + Cortex Debug extension**
* **ST-Link v2** programmer (or equivalent)

---

## 📍 Hardware

**Board:** Blue Pill – STM32F103C8T6

**Onboard LED pin:**

* LED → **PC13** (Active LOW)

There is no external wiring needed.

---

## 📁 Project Structure

```
STM32-Blinky-HAL/
├── Core/
│   ├── Inc/
│   │   └── main.h
│   ├── Src/
│   │   ├── main.c
│   │   └── stm32f1xx_it.c
├── Drivers/
│   ├── CMSIS/
│   └── STM32F1xx_HAL_Driver/
└── README.md
```

---

## ⚙️ GPIO Configuration

In **STM32CubeMX**:

* Set **PC13** as *GPIO_Output*
* Keep default settings for clock configuration
* Generate project code

CubeMX generates the `MX_GPIO_Init()` function automatically.

---

## 💡 Main Code Example

Here is the core of the LED toggle logic:

```c
while (1)
{
    HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13); // Toggle onboard LED
    HAL_Delay(500); // Wait 500 ms
}
```

---

## ▶️ How to Build and Flash

### **1. Open the project**

Import or open the generated project in your chosen IDE.

### **2. Compile**

Build the project — ensure there are no errors.

### **3. Connect ST-Link**

Plug ST-Link to the Blue Pill and your PC.

### **4. Flash the firmware**

Click **Download/Flash** in your IDE.

Your Blue Pill should now blink the onboard LED every 500 ms.

---

## 🧪 Testing

If everything is correct, the LED next to the USB connector (PC13) will:

* Blink **slowly**: working correctly
* Stay ON/OFF: check wiring, ST-Link, or clock config

---

## 📄 License

This project is released under the **MIT License**. Feel free to use it in your own work.

---

## ⭐ Contributions

Pull requests are welcome — especially improvements for beginners or alternative build setups.

---

Happy hacking with STM32! 🚀
