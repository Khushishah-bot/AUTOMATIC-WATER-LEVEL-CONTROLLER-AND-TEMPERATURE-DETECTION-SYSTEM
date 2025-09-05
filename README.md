# AUTOMATIC-WATER-LEVEL-CONTROLLER-AND-TEMPERATURE-DETECTION-SYSTEM
The "Automatic Water Level Sensor and Controller System" uses Arduino, ultrasonic sensor, DS18B20, relay, LCD, and a water pump to manage water levels efficiently. It automates pump control (ON &lt;30%, OFF >97%), prevents overflow/dry run, monitors temperature, and displays status, reducing wastage and improving resource management.
Methodology:
 Circuit  Diagram:
<img width="1200" height="569" alt="Screenshot 2025-09-06 012830" src="https://github.com/user-attachments/assets/7b344a14-8d1d-4a99-8695-496af851e7cc" />
Ultrasonic Sensor:
The ultrasonic sensor is positioned at the top of the water tank to measure the distance from the sensor to the water surface. It uses sound waves to detect the water level and sends this information to the microcontroller for processing. Based on the distance, the water level is calculated and compared with predefined thresholds (30% and 97%).
DS18B20 Temperature Sensor:
The DS18B20 sensor continuously measures the temperature of the water. This data is sent to the microcontroller and displayed on the LCD to give the user a complete understanding of the tank's status.
Microcontroller (Arduino):
The Arduino acts as the central unit that processes inputs from both the ultrasonic and temperature sensors. It also controls the output, including activating or deactivating the pump. The Arduino is programmed to turn on the pump when the water level falls below 30% and turn it off when it rises above 97%. It also sends information to the LCD for real-time display.
Relay:
The relay module acts as an interface between the Arduino and the 220V water pump. When the Arduino determines that the water level is low (below 30%), it sends a signal to the relay, which then closes the circuit and turns the pump on. When the water level exceeds 97%, the Arduino sends a signal to open the relay and turn off the pump.
LCD Display:
The LCD display (16x2 I2C) shows real-time information such as the water level (in percentage), pump status (ON/OFF), and the water temperature. This display allows users to easily monitor the system without needing external tools or software.
Power Supply:
The system requires a power supply to operate the Arduino, sensors, and LCD. It typically uses a 5V supply for the Arduino and sensors, while the relay and water pump require a separate 220V AC power supply. The power supply ensures all components function properly without interruptions.

Components Used 

Ultrasonic Sensor (HC-SR04)
The ultrasonic sensor is a widely used sensor that measures distances by emitting sound waves and analysing their reflection. In this system, the ultrasonic sensor is used to measure the water level in a tank, a critical task for the Automatic Water Level Sensor and Controller.
How It Works?
The ultrasonic sensor operates using a basic principle of sound wave propagation. It emits high-frequency sound waves, typically in the range of 40 kHz, and then measures the time it takes for the sound waves to travel to an object (in this case, the water surface) and reflect back to the sensor. This round-trip time is then used to calculate the distance between the sensor and the object.
Emission of Sound Waves:
The ultrasonic sensor emits a short burst of high-frequency sound waves, which travel outward at the speed of sound.
Reflection from the Water Surface:
The sound waves travel through the air until they hit an object—in this case, the surface of the water. The sound waves are reflected back towards the sensor.
Time Measurement:
The sensor measures the time taken for the sound waves to travel to the water surface and return. This time is directly proportional to the distance between the sensor and the water surface.
Key Features of Ultrasonic Sensors
Non-Contact Measurement:
The ultrasonic sensor does not require direct contact with the water, making it ideal for water level detection, as it is immune to the challenges posed by water impurities, floating debris, or contamination.
Accuracy:
The ultrasonic sensor provides accurate distance measurements within a specific range, typically 2 cm to 4 meters for the popular HC-SR04 model. This high accuracy ensures precise water level monitoring.

Simplicity and Low Cost:
Ultrasonic sensors are relatively simple to use, inexpensive, and widely available, making them an ideal choice for small-scale applications like this water level monitoring system.
Robustness:
These sensors are robust in a variety of environments, including those with varying temperatures or humidity, which is particularly beneficial in applications involving water.

DS18B20 Temperature Sensor
The DS18B20 is a highly accurate, digital temperature sensor manufactured by Maxim Integrated. It is widely used in a variety of applications, such as home automation, industrial systems, weather stations, and environmental monitoring, due to its simplicity, cost-effectiveness, and precision. The sensor operates on a 1-Wire protocol, which allows for data transmission over a single data line, simplifying wiring and communication.
Key Features of the DS18B20 Sensor:
Digital Output:
Unlike analogue temperature sensors, the DS18B20 provides a digital output, making it easy to interface with digital systems like microcontrollers (e.g., Arduino). This eliminates the need for analogue-to-digital conversion (ADC), which is necessary for other temperature sensors.
Wide Temperature Range:
The sensor can measure temperatures between -55°C and +125°C with a resolution of 9 to 12 bits, allowing for temperature readings with high accuracy. The default resolution is typically 12 bits, which provides a precision of 0.0625°C.
Wire Interface:
One of the defining features of the DS18B20 is its 1-Wire interface, which means that it can communicate with a microcontroller over a single wire for data transmission. The data line is used for both communication and power, simplifying the system setup. Multiple DS18B20 sensors can also be connected to the same data line in a "daisy-chaining" configuration, which is useful for systems requiring multiple temperature readings.
Power Supply:
The DS18B20 operates on a voltage range of 3.0V to 5.5V, making it compatible with a wide range of systems. It can be powered in two ways: parasitic power mode or external power mode. In parasitic mode, it draws power from the data line, reducing the need for an additional power source, while in external power mode, it uses a dedicated power supply.
High Accuracy:
The DS18B20 sensor offers a high level of precision. With a typical accuracy of ±0.5°C within the range of -10°C to +85°C, it is well-suited for applications requiring precise temperature measurements. This accuracy makes it ideal for environments like aquaculture, industrial equipment monitoring, or any system where temperature control is critical.
How DS18B20 Works:
Initialization:
The DS18B20 is initialized by sending a reset pulse on the 1-Wire data line. After initialization, the sensor can be configured for the desired resolution, which determines how frequently it can provide temperature updates.
Temperature Conversion:
Once initialized, the sensor continuously measures the temperature of its environment. The DS18B20 converts the analog temperature into a digital format, which is stored in a 16-bit register. The sensor then transmits this data via the 1-Wire bus to the microcontroller.
Reading Temperature Data:
To obtain the temperature data, the microcontroller sends a command over the 1-Wire bus to the sensor, requesting the temperature reading. The DS18B20 responds by transmitting a 16-bit temperature value, which can then be interpreted as a temperature in Celsius or Fahrenheit, depending on the system configuration.
Applications of DS18B20:
Water Tanks:  In applications like the automatic water level sensor and controller system, the DS18B20 sensor is used to monitor water temperature, ensuring the water remains within optimal temperature ranges for aquaculture, industrial processes, or simply maintaining comfort in residential tanks.
Environmental Monitoring:  It is commonly used in weather stations, greenhouses, and climate-controlled environments where precise temperature measurements are essential.
Home Automation:  DS18B20 sensors are frequently used in smart home systems to monitor the temperature of rooms, HVAC systems, and other areas where temperature regulation is critical.
Industrial Equipment:  In industrial systems, temperature monitoring is vital to ensure the proper functioning of machinery and prevent overheating or failure.
Arduino: An Overview
Arduino is an open-source electronics platform based on simple software and hardware. It is widely used by hobbyists, engineers, and educators for creating interactive projects. Arduino boards are equipped with microcontrollers that can be programmed to interact with sensors, motors, displays, and other electronic components. Due to its versatility, ease of use, and large community support, Arduino has become a popular choice for both beginners and experienced developers.
Key Features of Arduino:
Microcontroller-Based:
At the heart of every Arduino board is a microcontroller, a small integrated circuit that executes programmed instructions. The microcontroller reads inputs from sensors and control devices like LEDs or motors based on the instructions provided in the program.
Open-Source Hardware and Software:
Arduino is open-source, meaning both its hardware and software designs are freely available for modification and distribution. This has led to a large and active community that contributes to its development and shares resources.
User-Friendly IDE (Integrated Development Environment):
The Arduino IDE is simple and easy to use, especially for beginners. It supports C++ programming and comes with built-in libraries for interfacing with various components (sensors, motors, displays, etc.), so users don’t need to write all the low-level code from scratch.
Wide Range of Compatible Boards:
Arduino offers various types of boards that cater to different needs. The most common board is the Arduino Uno, which uses the ATmega328P microcontroller. However, other variants like the Arduino Nano, Arduino Mega, and Arduino Leonardo offer different I/O options, memory capacities, and processing power to suit different project requirements.
I/O Pins:
Arduino boards come with a number of digital and analog input/output (I/O) pins. These pins can be used to read signals from sensors (input) or send signals to actuators like motors or lights (output). For example, a digital pin can read the state of a switch (HIGH or LOW) or control an LED, while an analog pin can read values from sensors such as temperature sensors or potentiometers.
Serial Communication:
Arduino can communicate with other devices or computers via serial communication. This allows data to be transferred between Arduino and other devices such as computers, Bluetooth modules, or Wi-Fi shields.
Ease of Integration with Sensors and Actuators:
Arduino boards are designed to work seamlessly with a wide range of sensors (e.g., temperature, ultrasonic, humidity) and actuators (e.g., motors, relays, LEDs). It has numerous libraries and shields to make these integrations quick and simple.
Real-Time Control:
Arduino operates in real-time, meaning it can continuously monitor inputs (like water levels from sensors) and provide outputs (e.g., controlling a pump) in response to changes. This makes it suitable for projects that require automation, like the Automatic Water Level Sensor and Controller System.
How Arduino Works:
Programming the Arduino:
Arduino boards are programmed using the Arduino IDE, which is available for Windows, macOS, and Linux. The IDE provides a simple interface where you can write the program (called a sketch) and upload it to the Arduino board via a USB connection. The programming language used is a simplified version of C/C++.
Processing Inputs and Outputs:
The Arduino reads input data from sensors connected to its pins. For example, an ultrasonic sensor might be connected to a digital input pin to measure the distance from the sensor to an object. Based on the input values, the Arduino can take actions, such as turning on an LED, controlling a motor, or triggering a relay.
Real-Time Execution:
Once the program is uploaded, the Arduino runs continuously in a loop, constantly checking the inputs and executing the programmed tasks. For instance, in the water level monitoring project, the Arduino will check the water level using the ultrasonic sensor and turn the pump on or off based on predefined conditions.
Serial Communication:
The Arduino can send and receive data to/from a computer or other devices through the serial port. This is especially useful for debugging, logging sensor data, or controlling the Arduino remotely.
LCD I2C Display Overview
LCD I2C display is one of the common interfaces that display information in many electronics projects, especially those who require microcontrollers, like Arduino. It combines the flexibility of a standard 16x2 LCD (Liquid Crystal Display) with the easiness of an I2C (Inter-Integrated Circuit) interface and simplifies the wiring and communication.
Key Features of the LCD I2C Display:
16x2 Character Display:
The most common version of LCD I2C displays is the 16x2, referring to 16 characters per line and 2 lines of text. That adds up to 32 characters on the screen. That is usually enough for most simple displays, such as the sensor readings, status messages, or control options.
I2C Interface:
The I2C interface is a dual-wire interface that is used to communicate the display and the microcontroller. This is done with two wires, labeled the SDA (Serial Data Line) and SCL (Serial Clock Line). This helps in reducing the number of pins required on the microcontroller, especially in devices that use few I/O pins, such as is the case with the Arduino Uno. Backlight:
Most LCD I2C displays come with a pre-installed backlight which illuminates the screen. This makes reading extremely easy even in low-light conditions. Low power consumption applies to most of these displays, hence the control is usually done from one pin or by a potentiometer, such that it can be set.
These displays consume virtually no power, making them well-suited for battery powered applications. The I2C interface also achieves this: number of connections is reduced along with communication overhead.
Simplified Wiring
16x2 LCDs require 16 data pins connected to the microcontroller. However, when using the I2C module, you only need to connect four wires namely GND, VCC, SDA and SCL. It is also easier compared to others in terms of wiring setup.
Easy Integration with Microcontrollers
I2C LCD is widely used with microcontrollers, such as Arduino, Raspberry Pi, and other embedded systems. You can easily control it through libraries available in the Arduino IDE that simplify the programming process.
How LCD I2C Works:
I2C Communication:
The LCD I2C module is based on the I2C protocol wherein many devices share the same data and clock lines. The microcontroller communicates with the LCD by sending commands and data to the I2C controller chip, which, in turn, forwards the content to be displayed to the LCD's internal controller.
SDA: These are the data lines that can be used for sending as well as receiving data.
SCL: This is the clock line that synchronizes the data transfer between devices.
I2C protocol is half duplex; in other words, only one direction can be allowed to flow at a time, but due to its efficiency, and it can handle many devices on the same bus line, makes it ideal for many embedded applications.
Display Initialization:
Initializing the module of the LCD I2C also requires you to initialize display settings like cursor position, text size, and control backlight at the power-up. Also check whether the connection between the LCD and the microcontroller is good..
Advantages of Using LCD I2C Displays
Less Number of Pins:
I2C communication allows data transmission via two wires, namely SDA and SCL. It needs only these two lines to communicate whereas the common 16x2 LCD has to be connected with 16 wires of data. This saves the projects where an extra I/O pin is not available, like in Arduino Uno or any small type of microcontrollers.
Easy Connection:
The LCD I2C display goes a long way toward reducing complexity of wiring compared to the standard parallel LCDs. They have fewer wires, and much less space is required, making the I2C version significantly easier to use and manage, mostly in large projects.
Multiple Displays:
Since I2C allows multiple devices on the same bus, you can attach dozens of I2C devices, such as several LCD displays, to the microcontroller using as little as two lines (SDA and SCL) provided that every device has a unique address. This scale and distributability makes scaling your project from one or two displays to multiple easy.
Small Footprint:
LCD I2C displays are more compact than parallel displays. They are perfect to use in projects where the space becomes an issue, such as in wearable devices, robots, or small enclosures.
Low Power Consumption:
The I2C interface is very power-efficient which is excellent for battery-operated projects. The LCD itself is a low power component and the I2C bus protocol minimizes the power usage on the bus.
5V Relay:
A 5V relay is an electrically operated switch that allows a low voltage (e.g., 5V from a microcontroller like Arduino) to control high-voltage circuits (e.g., 220V AC for a water pump). It has two main parts: the coil and the switching contacts. When the 5V signal is applied to the relay's coil, it creates a magnetic field that closes the contacts, allowing current to flow through the high-voltage circuit.
In the Project: The relay is used to control the 220V water pump. The Arduino sends a 5V signal to the relay to turn the pump on or off based on the water level detected by the ultrasonic sensor. The relay acts as an interface between the low-voltage Arduino and the high-voltage pump.
220V Water Pump:
A 220V water pump is a pump powered by an AC voltage of 220V, commonly used in household water pumping systems. It is designed to move water from one place to another, and it typically requires a high power supply to operate.
In the Project: The 220V pump is used to automatically pump water when the water level in the tank falls below a certain threshold (30%). The Arduino controls the pump through the 5V relay. When the water level is low, the Arduino sends a signal to the relay to turn on the pump, and when the water level reaches 97%, it sends a signal to turn off the pump, ensuring the water level stays within the desired range.
The combination of the 5V relay and 220V pump allows the project to control the water level in a tank automatically and safely.

The Working Principle of the Automatic Water Level Sensor & Controller System 
The Automatic Water Level Sensor & Controller System monitors the water level in the tank so that water pump will run automatically to maintain an optimum water level. Below is a detailed breakdown of how the system actually works 
 1. System Initialization: When the system is powered on, the Arduino initializes and runs the program. The TV I2C display initializes to demonstrate the water position, pump status, and the water temperature. The water temperature is displayed on the TV as the DS18B20 temperature detector is actuated to cover it. The Ultrasonic detector is turned on and water starts to measure its level. 
 2. Water Level Discovery using Ultrasonic Sensor: An ultrasonic detector works by emitting sound waves and measuring the time it takes for them to reflect off the water molecules and return back to the detector. This time is converted into a distance which corresponds to the water level in the tank. These distances are continuously checked by the Arduino to detect  the water  position in the tank.  
 3. Computation and Display of Water Level:  Once the distance to the water face is measured, Arduino calculates the chance of the water level in the tank and also displays on the TV.  For illustration, when the water position is veritably low, the ultrasonic detector will return a large distance value, indicating that the tank is nearly empty. When the tank reaches its maximum capacity, the detector will return a small distance value (representing near the top). The percent water level is also calculated and displayed on the TV to keep real- time monitoring. 
 
 4. Temperature Monitoring- Digital DS18B20 Temperature Detector: The DS18B20 temperature detector reads the current water temperature and also sends it back to Arduino. also, the temperature data is displayed on TV that would show water temperature. This data would be important for some operations; for case, monitoring conditions in the water or changing that temperature of water stays well within a certain range. 
 5. Pump ON/ OFF Control sense:  The Arduino reads the information coming from the ultrasonic detector and calculates about how long it should take to switch the pump on and off. Now, as the water  position falls below 30( the tank is nearly empty), the Arduino will  spark the 5V relay connected in this circuit, which will  shoot a signal to it and close the connections that allow current moving towards the water pump( 220V) to pass through the pump, turn it on. The pump will now pull in water into the tank.  Once the position of water reaches 97 that's when the tank is nearly full), Arduino will switch off the pump by controlling relay to OFF. This will lead to opening connections of the relay breaking the force of power to the water pump so as not to overfill the tank. It's an interlink between low voltage Arduino sense to a high- voltage circuit of the water pump. In then, the affair from Arduino 5V will spark the relay, which controls the 220V water pump. 
 
 6. Relay Operation: The Arduino uses the 5V relay in order to power the 220V pump. Below are the introductory factors of the relay. This still, in this trial, the coil amped by the 5V signal from the Arduino does produce a tremendous field. These are switching connections, which typically open or close when the coil is amped.  When the quantum reaches below 30, Arduino reads this and sends a 5V signal through the relay coil. The coil will close the connections on relay and supplies the 220V AC to the water pump. And the water pump will start working. Now, once the water position reaches 97, it cuts the relay by switching off the 5V signal. So, at this time, the relay connections open up and cut off the power force to the pump, automatically, the pump gets switched off. 
 7. Nonstop Monitoring and Updates: The system continuously monitors the water position and temperature, updates the TV display with the rearmost readings; therefore, the pump will turn on or off grounded on the water level.  The system also ensures that the pump only operates when necessary, conserving energy and precluding overflow. 8. Safety and Feedback For illustration, if there's a problem with the system; for case, failure of the ultrasonic detector or malfunction in the actuation in the relay, also one can program the Arduino to displays feedback or indeed an error communication on the TV, similar as" Error Sensor Failure" or" Error Relay Malfunction" to notify the stoner that commodity is wrong with the system. 



