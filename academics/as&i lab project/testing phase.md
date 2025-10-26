

### with html (using gemini)

![[random-repo/academics/as&i lab project/images/AI display parts.png]]
`above fig: attitude Indicator made by gemini using html and JavaScript`

#### what are the parts of the image

| Component              | Description                                                      | Unit                | Display Location |
| ---------------------- | ---------------------------------------------------------------- | ------------------- | ---------------- |
| **Attitude Indicator** | Shows aircraft pitch (nose up/down) and roll (wings left/right). | Degrees             | Center           |
| **Airspeed Indicator** | Shows speed of the aircraft through the air.                     | Knots (KTS)         | Left Tape        |
| **Altimeter**          | Shows aircraft height above sea level.                           | Feet (FT)           | Right Tape       |
| **Heading Indicator**  | Shows the direction the aircraft's nose is pointing.             | Degrees (HDG)       | Bottom Tape      |
| **Vertical Speed**     | Shows rate of climb or descent.                                  | Feet / Minute (V/S) | Far Right Column |
| **Roll Indicator**     | Digital and analog display of the precise roll angle.            | Degrees (ROLL)      | Top Center       |

---
### technical explanation of how this display works
#### How This HTML/JS Code Works

1. **Independent Data Simulation:** A `setInterval` loop runs in the background, acting like a "fake sensor." It constantly updates numbers for pitch, roll, and altitude to make them wobble realistically, like a plane in light turbulence.
    
2. **High-Speed Render Loop:** An entirely separate `requestAnimationFrame` loop runs as fast as your monitor can (usually 60+ times per second). Its only job is to re-draw the entire display.
    
3. **Canvas Drawing:** Each time the render loop runs, it clears the screen and calls functions like `drawAttitudeIndicator()` and `drawAirspeedTape()`. These functions read the latest numbers from the "fake sensor" and draw the tapes, lines, and numbers onto the HTML canvas.

#### How to Use This with a Real STM32 & MPU6050

1. **STM32 Replaces the Simulator:** Your STM32 board becomes the "brain." Its job is to read raw data from the MPU6050 (via I2C), process it (using a filter like a Kalman filter) to get stable pitch and roll angles, and read any other sensors you have (like a barometer for altitude).

>note: A **Kalman filter** is an algorithm that uses a series of noisy measurements over time to produce optimal estimates of a system's underlying state

2. **Send Data over Serial (UART):** The STM32 formats this clean data into a simple string (e.g., `P:10.5,R:-3.2,A:1500\n`) and sends it out over its UART (Serial) port 20-30 times per second.

>note: **UART (Universal Asynchronous Receiver-Transmitter)** is a serial communication protocol that transfers data between devices using two wires (transmit and receive) without a shared clock, requiring both devices to agree on speed and data format.

3. **JavaScript Listens for Serial Data:** You modify this HTML/JS code to use the **Web Serial API**. Instead of running the "fake data" function, your JavaScript will connect to the STM32's serial port, listen for the incoming strings, parse them, and update the `sensorData` object. The drawing loops will then automatically display the real-time data from your sensor.
---
### simpler explanation of the above one

#### How This Current Webpage Code Works

1. **It Has a "Fake Data" Robot:** Think of one part of the code as a robot on a timer. Every 30 milliseconds, its alarm goes off, and it writes down a new set of numbers (pitch, roll, speed) that are just _slightly_ different from the last set, making it look like a real, wobbly plane.
    
2. **It Has a "High-Speed Artist":** A second, totally separate part of the code is like an artist that can draw incredibly fast (60+ times per second). Its only job is to instantly erase the entire screen and re-draw everything (the horizon, the numbers, the tapes) from scratch.
    
3. **The Artist Peeks at the Robot's Numbers:** Before the Artist starts each new drawing, it takes a quick glance at the _latest numbers_ the "Fake Data" Robot wrote down. It uses those numbers to decide exactly _where_ to draw the horizon line and _what_ numbers to paint on the speed tape. This happens so fast, it looks like smooth animation.

#### How to Connect a Real STM32 Sensor

1. **The STM32 Becomes the "Brain":** The MPU6050 sensor is like your inner ear; it feels all the raw wobbles. The STM32 board is the "brain" that reads this raw data and "cleans it up" into simple, stable numbers, like `Pitch = 10.5` and `Roll = -3.2`.
    
2. **The STM32 Shouts Numbers Over USB:** The STM32's job is to package these clean numbers into a simple text message (like `"P:10.5, R:-3.2\n"`) and send it over the USB cable to the computer, over and over, 30 times a second.
    
3. **The Webpage Listens for the "Shouts":** You modify this webpage's JavaScript code. You _delete_ the "Fake Data" Robot and replace it with a "Listener." This "Listener" pays attention to the computer's USB port. When that text message arrives from the STM32, the Listener grabs it, updates the numbers, and the "High-Speed Artist" (which is still running) automatically draws the display using these _real_ numbers.
---
### how to do this with the hardware

1. **STM32 (CubeIDE):** Your C code **reads** the 6-axis sensor, **filters** the raw gyro/accel data into stable `pitch` and `roll` angles, and **prints** them as a simple text string over the USB (as a UART/COM port), ending with a newline (e.g., `"P:10.5,R:-3.2\n"`).
    
2. **HTML (Browser):** You click "Connect," and the JavaScript uses the **Web Serial API** to find and listen to your board's COM port.
    
3. **PFD (The Link):** The JavaScript **parses** the incoming text strings, updates the `sensorData` numbers, and the existing canvas-drawing loop automatically re-draws the PFD to match, showing real-time movement.
---

>NOTE (*date: 25-10-2025*)
>- **original project Statement**: Turn \& Bank Indicator: Microcontroller based computation of roll rate and displays turn coordination graphically.
>- this is just a testing phase, just to check the GUI. the above mentioned features will be updated in the future phases.

