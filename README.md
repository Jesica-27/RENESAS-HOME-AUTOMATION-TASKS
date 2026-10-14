# Renesas RA Microcontroller – Embedded Firmware Tasks

## 📌 Project Overview

This project focuses on learning and implementing low-level embedded firmware development using a Renesas RA microcontroller. The work involves direct register-level programming to configure the system clock, GPIO pins, switches, LEDs, and hardware timers.

The project is being developed task by task to understand how microcontroller peripherals operate at the register level without depending entirely on high-level driver APIs.

## 🎯 Objectives

- Understand the clock configuration of a Renesas RA microcontroller.
- Configure GPIO pins for digital input and output.
- Interface switches and LEDs using hardware registers.
- Implement logical operations using switch inputs.
- Configure the GPT0 timer for periodic event generation.
- Develop a strong foundation in embedded C and low-level peripheral programming.

## 🛠️ Hardware and Software

**Hardware**
- Renesas RA microcontroller development board
- Onboard switches
- Onboard LED

**Software and tools**
- Embedded C
- Renesas Flexible Software Package (FSP) project environment
- `hal_data.h`
- Renesas IDE and compiler toolchain

## ✅ Task 1: GPT0 Timer-Based LED Toggling

### Objective
Configure the General PWM Timer (GPT0) to generate periodic timer events and toggle an LED after a specified number of events.

### Working Principle
1. Configure the high-speed on-chip oscillator (HOCO) and system clock.
2. Configure the LED pin as a GPIO output.
3. Enable the GPT0 peripheral module.
4. Set the timer period and prescaler.
5. Start GPT0 and monitor its event flag.
6. Increment a software counter whenever the timer event occurs.
7. Toggle the LED when the counter reaches the configured threshold.

### Key Concepts
- Clock initialization
- GPT0 timer configuration
- Prescaler and timer period calculation
- Timer event flag polling
- GPIO output control

**Status:** Completed according to the current implementation.

## ✅ Task 2: XOR Logic Using Two Switches

### Objective
Control an LED based on the XOR (Exclusive OR) operation applied to two switch inputs.

### GPIO Configuration

| Pin | Function |
|---|---|
| P103 | SW2 input |
| P104 | LED output |
| P105 | SW1 input |

### Working Principle

1. Initialize the system clock.
2. Configure P103 and P105 as switch inputs.
3. Configure P104 as an LED output.
4. Read both switch states using the port input register.
5. Convert the active-low switch readings into logical values.
6. Perform the XOR operation on the two inputs.
7. Turn the LED ON when the XOR result is 1; otherwise, turn it OFF.

### XOR Truth Table

| SW1 | SW2 | XOR Result | LED |
|---:|---:|---:|---|
| 0 | 0 | 0 | OFF |
| 0 | 1 | 1 | ON |
| 1 | 0 | 1 | ON |
| 1 | 1 | 0 | OFF |

*Here, 1 represents a pressed switch after active-low conversion.*

### Key Concepts
- GPIO input and output configuration
- Port input and output registers
- Active-low switch handling
- Bitwise operations
- XOR logic implementation
- Register-level programming

**Status:** Completed according to the current implementation.

## 📚 Concepts Learned

- Direct memory-mapped register access
- Use of `volatile` for hardware register access
- System clock configuration
- GPIO pin direction and state control
- Timer prescaler and period configuration
- Polling-based peripheral handling
- Bitwise masking and logical operations
- Converting hardware input states into logical values

## 🚀 Future Enhancements

- Implement switch debouncing.
- Explore interrupt-based timer handling.
- Add additional GPIO and timer experiments.
- Explore PWM generation and duty-cycle control.
- Configure other microcontroller peripherals.
- Improve code modularity and peripheral initialization.

## 📈 Project Status

This is an ongoing embedded firmware learning project. The first two tasks have been implemented, covering timer-based LED control and switch-based XOR logic. Additional tasks and peripheral experiments will be added as development progresses.

## 👩‍💻 Domain

**Embedded Systems | Embedded C | Renesas RA | GPIO | GPT Timer | Register-Level Programming**
