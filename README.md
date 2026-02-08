# 🌡️ CODTECH Internship – Task 3

## Temperature Monitoring / Serial-Based Control System Using Arduino

### Internship Program: **CODTECH**

**Task:** Use a temperature sensor to read and display temperature data on an LCD or Serial Monitor
**Instructions:** Temperature Monitoring System
**Deliverables:** Circuit Design, Source Code, and Output Demonstration

---

## 📌 Project Description

This project demonstrates a **serial-based monitoring and control system** using an **Arduino Uno**.
Commands are sent through the **Serial Monitor** to control connected devices such as a **light** and a **fan**.

The system displays received commands and device status on the **Serial Monitor**, demonstrating basic monitoring and control using serial communication.

The project fulfills all requirements specified in **CODTECH Internship Task-3**.

---

## 🎯 Objectives

* Implement serial-based monitoring using Arduino
* Control devices through Serial Monitor commands
* Display system status and outputs on Serial Monitor
* Demonstrate embedded system control logic

---

## 🔧 Hardware Components

| Component                   | Quantity    |
| --------------------------- | ----------- |
| Arduino Uno                 | 1           |
| Relay Module (2-Channel)    | 1           |
| Light (LED / Bulb for demo) | 1           |
| Fan (Motor / LED for demo)  | 1           |
| Breadboard                  | 1           |
| Jumper Wires                | As required |

---

## 🔌 Circuit Connections

### Device Connections

* **Light Relay IN** → Arduino Pin **8**
* **Fan Relay IN** → Arduino Pin **9**
* **Relay VCC** → 5V
* **Relay GND** → GND

*(Serial communication used for command input)*

---

## 🧠 Working Principle

* User sends numeric commands through the Serial Monitor
* Arduino reads incoming serial data
* Based on the command, devices are switched ON or OFF
* System prints feedback and status messages on the Serial Monitor

---

## 💻 Arduino Source Code

```cpp
char data = 0;

void setup() {
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  Serial.begin(9600);

  Serial.println("HOME AUTOMATION SYSTEM");
  Serial.println("Commands:");
  Serial.println("1 = Light ON");
  Serial.println("2 = Light OFF");
  Serial.println("3 = Fan ON");
  Serial.println("4 = Fan OFF");
}

void loop() {
  if (Serial.available() > 0) {
    data = Serial.read();

    if (data == '\n' || data == '\r') return;

    Serial.print("Received: ");
    Serial.println(data);

    if (data == '1') {
      digitalWrite(8, HIGH);
      Serial.println(">> Light: ON");
    }
    else if (data == '2') {
      digitalWrite(8, LOW);
      Serial.println(">> Light: OFF");
    }
    else if (data == '3') {
      digitalWrite(9, HIGH);
      Serial.println(">> Fan: ON");
    }
    else if (data == '4') {
      digitalWrite(9, LOW);
      Serial.println(">> Fan: OFF");
    }
    else {
      Serial.print(">> ERROR: ");
      Serial.print(data);
      Serial.println(" is invalid!");
    }
  }
}
```

---

## 🔌 Circuit Diagram

![Circuit Diagram](https://github.com/radhikasatavkar12-tech/Task3/blob/main/task%203.png)

---

## 📟 Output Demonstration

### Serial Monitor Output

```
HOME AUTOMATION SYSTEM
Commands:
1 = Light ON
2 = Light OFF
3 = Fan ON
4 = Fan OFF

Received: 1
>> Light: ON
Received: 4
>> Fan: OFF
```

* Devices respond instantly to serial commands
* System displays command feedback clearly

---

## 📟 Output Demonstration

![Serial Output](https://github.com/radhikasatavkar12-tech/Task3/blob/main/task%203%20output.png)

---

## ✅ Task Completion Checklist

✔ Serial monitoring implemented
✔ Device control via commands
✔ Output displayed on Serial Monitor
✔ Circuit design completed
✔ Output demonstrated

---

## 🏁 Conclusion

This project successfully demonstrates a **serial-based monitoring and control system** using Arduino.
It showcases command handling, device control, and real-time feedback through the Serial Monitor, fulfilling all requirements of **CODTECH Internship Task-3**.


Just tell me 👍
