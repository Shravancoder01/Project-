# 🤖 Human Following Robot using Arduino, IR & Ultrasonic Sensors

A smart Arduino-based robot that detects and follows human movement using **IR sensors** and maintains a safe distance using an **ultrasonic sensor**. The robot can turn left, right, or move forward depending on hand gestures and proximity. Ideal for robotics learners and gesture-controlled systems.


## Project Structure



## 🔧 Components Used

| Component                      | Quantity | Description                                  |
|-------------------------------|----------|----------------------------------------------|
| Arduino Uno                   | 1        | Microcontroller board                        |
| IR Sensor Module              | 2        | For detecting hand gestures (left/right)     |
| Ultrasonic Sensor (HC-SR04)   | 1        | For human distance detection                 |
| L298N Motor Driver Module     | 1        | Controls DC motors using PWM                 |
| DC Gear Motors                | 2        | For robot movement                           |
| Wheels + Chassis              | 1 Set    | Mechanical support for mobility              |
| Power Supply (Battery)        | 1        | External power for motors                    |
| Breadboard & Jumper Wires     | As req.  | Circuit connections                          |


## ⚙️ Circuit Connection Table

### ➤ IR Sensors

| Sensor          | Arduino Pin |
|----------------|-------------|
| IR Right       | 2           |
| IR Left        | 3           |

### ➤ Ultrasonic Sensor (HC-SR04)

| Pin     | Arduino Pin |
|---------|-------------|
| Trig    | 11          |
| Echo    | 12          |

### ➤ Right Motor (via L298N)

| Motor Pin       | Arduino Pin |
|-----------------|-------------|
| Enable A        | 5           |
| IN1             | 7           |
| IN2             | 8           |

### ➤ Left Motor (via L298N)

| Motor Pin       | Arduino Pin |
|-----------------|-------------|
| Enable B        | 6           |
| IN3             | 9           |
| IN4             | 10          |

## 💡 How It Works

1. **IR Sensors** detect hand gestures:
   - Hand on right → turn right.
   - Hand on left → turn left.
2. **Ultrasonic Sensor** measures distance:
   - If person is 10–30 cm ahead → move forward.
   - Else → stop.
3. **PWM Control** adjusts motor speed smoothly for turning and following.
4. **Modular Function** `rotateMotor()` simplifies movement control logic.

---

## 🧠 Main Logic Flow (in `loop()`)

| Condition                                         | Action                         |
|--------------------------------------------------|--------------------------------|
| Right IR = LOW, Left IR = HIGH                   | Turn Right                     |
| Right IR = HIGH, Left IR = LOW                   | Turn Left                      |
| Both IR = HIGH, Distance between 10–30 cm        | Move Forward                   |
| Otherwise                                        | Stop Motors                    |

---

## 🧪 How to Use

1. **Install Required Library**:  
   - Go to Arduino IDE > Library Manager → Search & Install: `NewPing`

2. **Upload the Code**:  
   - Copy `human_following_robot.ino` into Arduino IDE  
   - Select Board: `Arduino Uno`  
   - Upload using USB cable

3. **Power Setup**:  
   - Motors need external power (6V–12V battery recommended)
   - Arduino can run via USB or VIN pin

---

## 📸 Images & Circuit Diagram

> Save the following files inside the `/Images/` folder.

| Preview              | File Path                  |
|----------------------|----------------------------|
| Circuit Diagram       | `Images/circuit_diagram.png` |
| Robot in Action       | `Images/output_demo.jpg`     |

Embed in `README` like:

