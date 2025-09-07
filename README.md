# AUTOMATIC-WATER-LEVEL-CONTROLLER-AND-TEMPERATURE-DETECTION-SYSTEM
The "Automatic Water Level Sensor and Controller System" uses Arduino, ultrasonic sensor, DS18B20, relay, LCD, and a water pump to manage water levels efficiently. It automates pump control (ON &lt;30%, OFF >97%), prevents overflow/dry run, monitors temperature, and displays status, reducing wastage and improving resource management.
 Circuit  Diagram:
<img width="1200" height="569" alt="Screenshot 2025-09-06 012830" src="https://github.com/user-attachments/assets/7b344a14-8d1d-4a99-8695-496af851e7cc" />
Components Used-

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



The Working Principle of the Automatic Water Level Sensor & Controller System 
The Automatic Water Level Sensor & Controller System monitors the water level in the tank so that water pump will run automatically to maintain an optimum water level. Below is a detailed breakdown of how the system actually works 
 1. System Initialization: When the system is powered on, the Arduino initializes and runs the program. The TV I2C display initializes to demonstrate the water position, pump status, and the water temperature. The water temperature is displayed on the TV as the DS18B20 temperature detector is actuated to cover it. The Ultrasonic detector is turned on and water starts to measure its level.

 2. Water Level Discovery using Ultrasonic Sensor: An ultrasonic detector works by emitting sound waves and measuring the time it takes for them to reflect off the water molecules and return back to the detector. This time is converted into a distance which corresponds to the water level in the tank. These distances are continuously checked by the Arduino to detect  the water  position in the tank.
  
 3. Computation and Display of Water Level:  Once the distance to the water face is measured, Arduino calculates the chance of the water level in the tank and also displays on the TV.  For illustration, when the water position is veritably low, the ultrasonic detector will return a large distance value, indicating that the tank is nearly empty. When the tank reaches its maximum capacity, the detector will return a small distance value (representing near the top). The percent water level is also calculated and displayed on the TV to keep real- time monitoring. 
 
 4. Temperature Monitoring- Digital DS18B20 Temperature Detector: The DS18B20 temperature detector reads the current water temperature and also sends it back to Arduino. also, the temperature data is displayed on TV that would show water temperature. This data would be important for some operations; for case, monitoring conditions in the water or changing that temperature of water stays well within a certain range.
     
 5. Pump ON/ OFF Control sense:  The Arduino reads the information coming from the ultrasonic detector and calculates about how long it should take to switch the pump on and off. Now, as the water  position falls below 30( the tank is nearly empty), the Arduino will  spark the 5V relay connected in this circuit, which will  shoot a signal to it and close the connections that allow current moving towards the water pump( 220V) to pass through the pump, turn it on. The pump will now pull in water into the tank.  Once the position of water reaches 97 that's when the tank is nearly full), Arduino will switch off the pump by controlling relay to OFF. This will lead to opening connections of the relay breaking the force of power to the water pump so as not to overfill the tank. It's an interlink between low voltage Arduino sense to a high- voltage circuit of the water pump. In then, the affair from Arduino 5V will spark the relay, which controls the 220V water pump. 
 
 6. Relay Operation: The Arduino uses the 5V relay in order to power the 220V pump. Below are the introductory factors of the relay. This still, in this trial, the coil amped by the 5V signal from the Arduino does produce a tremendous field. These are switching connections, which typically open or close when the coil is amped.  When the quantum reaches below 30, Arduino reads this and sends a 5V signal through the relay coil. The coil will close the connections on relay and supplies the 220V AC to the water pump. And the water pump will start working. Now, once the water position reaches 97, it cuts the relay by switching off the 5V signal. So, at this time, the relay connections open up and cut off the power force to the pump, automatically, the pump gets switched off.
    
 7. Nonstop Monitoring and Updates: The system continuously monitors the water position and temperature, updates the TV display with the rearmost readings; therefore, the pump will turn on or off grounded on the water level.  The system also ensures that the pump only operates when necessary, conserving energy and precluding overflow. 8. Safety and Feedback For illustration, if there's a problem with the system; for case, failure of the ultrasonic detector or malfunction in the actuation in the relay, also one can program the Arduino to displays feedback or indeed an error communication on the TV, similar as" Error Sensor Failure" or" Error Relay Malfunction" to notify the stoner that commodity is wrong with the system. 





