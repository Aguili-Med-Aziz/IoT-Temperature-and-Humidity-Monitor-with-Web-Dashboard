# IoT-Temperature-and-Humidity-Monitor-with-Web-Dashboard
Project Overview:
This project is a complete embedded system that monitors environmental temperature and humidity, and sends the data to a cloud server for visualization. The system is based on a microcontroller (such as an Arduino or ESP32), integrates sensors (e.g., DHT11/DHT22 for temperature and humidity), and uses a simple web dashboard to display live sensor data. This project demonstrates skills in sensor interfacing, wireless communication, cloud integration, and web dashboard development.

Project Details:
Project Objective:
Design and implement an IoT-based temperature and humidity monitoring system that:

Collects sensor data: Reads temperature and humidity values from DHT11/DHT22 sensors.
Processes data: Filters the sensor data for accuracy and stability.
Sends data: Transmits data wirelessly to a cloud service (e.g., ThingSpeak or AWS IoT Core).
Visualizes data: Displays live data on a web dashboard.
Hardware:
Microcontroller: Arduino Uno or ESP32/ESP8266.
Sensor: DHT11 or DHT22 for temperature and humidity.
Power Supply: USB power or battery (for portability).
Optional: OLED display to show data locally.
Software:
Firmware: C/C++ using the Arduino IDE or PlatformIO.
Cloud Platform: ThingSpeak, AWS IoT Core, or similar (for storing and visualizing data).
Web Dashboard: HTML, CSS, JavaScript (using libraries like Chart.js for data visualization).
Key Features:
Data Collection:

The system reads data from the DHT11/DHT22 sensors.
Includes data filtering (e.g., smoothing algorithms) to reduce sensor noise.
Wireless Communication:

The microcontroller communicates with a cloud platform via Wi-Fi (using ESP32 or ESP8266).
Data is sent to the cloud periodically (e.g., every 10 seconds).
Cloud Integration:

Uses ThingSpeak API to upload temperature and humidity data.
You can also use AWS IoT Core if you prefer more advanced cloud services.
Web Dashboard:

Data from the cloud is displayed in real-time on a web page.
A dashboard shows live graphs of temperature and humidity with JavaScript and Chart.js.
