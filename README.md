🇬🇧 [English version](README.md)
🇷🇺 [Russian version](README.ru.md)

![photo_2024-05-14_16-19-51](https://github.com/anneletta/Robot_Valli/assets/144317669/2c41621b-4c74-4718-9f6e-1c6a17d2538c)

Our robot consists of standard components: motors, a controller, two rechargeable batteries, radio modules, switches, a limit switch, a potentiometer, an RGB LED matrix, and a joystick.

**We used:**
- 1x Arduino Uno (+USB A-B)
- 1x Iskra Nano Pro (+USB Micro)
- 1x Motor Shield
- 2x NRF24L01+ radio modules
- 3x Li-ion 18650 batteries
- 1x battery holder
- 2x 12V DC motors with gearboxes
- 2x toggle switches
- 1x joystick
- 1x potentiometer
- 2x breadboards
- 2x NRF24L01 adapters

**Additional components:**
- Sensors, buttons
- Bolts, nuts
- Glue, tape, cable ties
- Servo drives, micro servo drives
- Limit switches
- Bearings

---

The robot's body was designed and 3D printed:

![3D](https://github.com/anneletta/Robot_Valli/assets/144317669/e9dc0ee2-87da-42fa-9e23-ff765d2cdc69)

---

Below is our step-by-step work on the robot, including the problems we faced and how we solved them:

### 1. Motor Assembly

After assembling the motor and connecting it to the board, we discovered that the solder between the motors and wires was weak. As a result, the wires came off the motors.

**Solution:** We re-soldered all the wires to the motors and glued them securely.

![pult_photo](https://github.com/anneletta/Robot_Valli/assets/144317669/b56f44e0-b1ed-4d36-945c-24cc8376bac9)

### 2. Remote Control

After assembling the remote control and double-checking the circuit diagram multiple times, we found that the remote was not sending any data to the computer. We decided to replace the Arduino Micro board and also replace the radio module with a new one. Despite these changes, the values still did not reach the computer. The sensitivity to joystick and toggle switch movements was ignored — only zero values (0.0) were being output.

The issue was identified and solved later during the motor-to-remote communication stage.

![provodki](https://github.com/anneletta/Robot_Valli/assets/144317669/7eb7f996-f5db-4418-ba46-8f0e3b554508)

### 3. Code for the Remote Control and Motor

Initially, we faced a problem where no code — not even test code — would compile. This was solved by installing additional required libraries.

Later difficulties were related to connecting the radio modules of the remote and the motor. The motor was programmed correctly, but it did not respond to joystick or toggle switch changes. As mentioned earlier, the joystick and toggle switch coordinates remained at zero the whole time.

We assumed that the remote's radio module was not detecting the motor's radio module. In the end, it turned out that all signals were being received properly. However, there was an error in the remote assembly: the connection was made to the wrong channel (one that did not match the code).

**Solution:** We changed the channel numbers in the code. The radio signal was successfully received, and the joystick and toggle switch became responsive.

---

**Worked on the robot:** Anna Deeva, Artem Krivushin, Lidzhi Ochirov

---


