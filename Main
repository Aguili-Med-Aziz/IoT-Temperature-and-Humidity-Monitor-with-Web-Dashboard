#include <DHT.h>
#include <WiFi.h>
#include <ThingSpeak.h>

#define DHTPIN 4            // Pin connected to the DHT sensor
#define DHTTYPE DHT22       // DHT 22 (AM2302) sensor
#define WIFI_SSID "yourSSID"
#define WIFI_PASSWORD "yourPassword"
#define CHANNEL_ID 123456   // Your ThingSpeak channel ID
#define WRITE_API_KEY "yourAPIKey"  // Your ThingSpeak write API key

DHT dht(DHTPIN, DHTTYPE);
WiFiClient client;

void setup() {
  Serial.begin(115200);
  dht.begin();
  WiFi.begin(WIFI_SSID, WIFI_PASSWORD);

  // Wait for WiFi to connect
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }
  Serial.println("Connected to WiFi");

  ThingSpeak.begin(client);  // Initialize ThingSpeak
}

void loop() {
  // Read temperature and humidity
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  // Check if any readings failed and exit early
  if (isnan(temperature) || isnan(humidity)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Display readings on Serial Monitor
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.print(" °C ");
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.println(" %");

  // Update ThingSpeak channel with new data
  ThingSpeak.setField(1, temperature);  // Field 1 for temperature
  ThingSpeak.setField(2, humidity);     // Field 2 for humidity
  ThingSpeak.writeFields(CHANNEL_ID, WRITE_API_KEY);

  delay(20000);  // Wait for 20 seconds before uploading new data
}
