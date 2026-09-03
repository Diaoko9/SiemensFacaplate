# Siemens WinCC Faceplate Library


This repository contains a collection of custom Siemens WinCC faceplates designed, tested, and implemented in real-world industrial projects.

A custom, reusable library of Siemens WinCC faceplates designed for industrial automation systems. This repository provides pre-configured graphic objects and tuning popups (`.PDL` files) to accelerate HMI development for standard process control applications. 

These faceplates are specifically optimized for projects utilizing standard STEP 7 PLC logic, offering a clean and lightweight alternative to the heavier, auto-generated SIMATIC PCS 7 CFC framework.

## 📦 Included Components

The library currently includes three main equipment modules, each complete with operator graphics and configuration popups:

*   **Motor / Pump Control:** Includes `pump.Pdl` for standard motor start/stop operations, status indications, and interlock monitoring.
*   **PID Controller:** Features `pid.Pdl` for the main loop faceplate and `pid_Tun.Pdl` for advanced tuning parameters (P, I, D values, and limits).
*   **Analog Transmitter:** Contains `tag.Pdl` for process value monitoring and `tag_Tun.Pdl` for scaling, alarm thresholds, and deadband configuration.

## ⚙️ System Requirements

*   **WinCC:** Siemens SIMATIC WinCC (v7.x or compatible).
*   **PLC:** Designed to interface seamlessly with standard STEP 7 Data Blocks (DBs) and User Data Types (UDTs).

## 🚀 How to Use

1.  Clone or download the repository to your local machine.
2.  Copy the desired `.PDL` files into the `GraCS` (Graphics) folder of your active WinCC project directory.
3.  Insert the faceplates into your process screens using a **Picture Window** object.
4.  Configure the **Tag Prefix** property of the Picture Window to point to your specific STEP 7 Data Block instance (e.g., `DB_PUMP_01.`).

## Transmitter Faceplate

![Screenshot 2024-07-26 041642](https://github.com/user-attachments/assets/86292af2-89e2-4c24-b338-853d49a63104)

![Screenshot 2024-07-26 041702](https://github.com/user-attachments/assets/17ecbf75-b88f-4947-83d3-1fb96b139cf3)

This faceplate is designed to monitor analog variables and manage alarm thresholds[cite: 2]. It displays the real-time variable value alongside its alarm states, and allows users to configure Zero/Span parameters. 

**Key Features:**
*   **Variable Monitoring:** Displays the Process Value (PV).
*   **Alarm States:** Visual indicators (H, HH, L, LL) appear automatically when the process value triggers specific switch values. 
    *   **HH:** High-High Switch Value
    *   **PH:** High Switch Value
    *   **PL:** Low Switch Value
    *   **LL:** Low-Low Switch Value
*   **Calibration Mode:** Using the "Cal" button, the operator can bypass the raw sensor input and inject a specific, desired value into the system for testing or calibration
*   **Tuning Mode:** A dedicated button in the bottom right corner allows the operator to seamlessly switch between Normal view and Tuning Mode to adjust alarm values

---

## Pump / Motor Faceplate

![Screenshot 2024-07-26 042544](https://github.com/user-attachments/assets/301db56b-44e1-4d96-b2d6-1e0bb24b9d76)

This faceplate provides a clean interface to control a pump and monitor its operational state

**Key Features:**
*   **Status Display:** The central black display area clearly indicates the current status of the pump (Start, Stop, or Electrical Fault)
*   **Command Controls:** Dedicated Start and Stop buttons are used to energize or de-energize the pump
*   **Action Feedback:** A dynamic ribbon located above the Start button provides visual feedback regarding the status of the start command

---

## PID Faceplate


![Screenshot 2024-07-26 043916](https://github.com/user-attachments/assets/1bfb0969-33cf-4efd-aa77-6f668ad73583)

![Screenshot 2024-07-26 043948](https://github.com/user-attachments/assets/e4754aca-da25-441f-a7d0-1b284b151c11)

The PID faceplate offers a comprehensive control interface for closed-loop processes

**Key Features:**
*   **Loop Monitoring:** Users can monitor the Process Value (PV), Setpoint Value (SV), and Manipulated Value (MV) directly from the main view
*   **Mode Switching:** A button below the faceplate allows the operator to toggle the loop status between Manual (Man) and Automatic (Auto)
*   **Tuning & Trending:** In Tuning Mode, engineers can adjust the PID coefficients[cite: 2]. This mode also features an integrated trend graph that plots PV, MV, and SV for real-time performance tracking

---

### Acknowledgements
These faceplates were created in collaboration with Eng. Karami Far

## 🤝 Contributing
Contributions, structural improvements, and bug fixes are welcome. Feel free to open an issue or submit a pull request.
