#define BLYNK_TEMPLATE_ID "TMPL3ZkPw2Oom"
#define BLYNK_TEMPLATE_NAME "THSData"
#define BLYNK_AUTH_TOKEN "twQcf2AGReqALkHVYRj1F-ivqBjL1YOW"   

// Include libraries
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <DHT.h>
#include <WiFi.h>
#include <BlynkSimpleEsp32.h>

// LCD settings
LiquidCrystal_I2C lcd(0x27, 16, 2);

// DHT11 settings
#define DHTPIN 4
#define DHTTYPE DHT11
DHT dht(DHTPIN, DHTTYPE);

// Soil moisture settings
#define SOIL_PIN 34

// LED settings
#define LED_PIN 2 // GPIO2 for the built-in LED on many ESP32 boards

// Wi-Fi credentials
char ssid[] = "SCET";                  // Replace with your Wi-Fi SSID
char pass[] = "SCET2024";              // Replace with your Wi-Fi Password

// Function to control LED
BLYNK_WRITE(V3) { // V3 is the virtual pin assigned to the LED button in Blynk
  int ledState = param.asInt(); // Get the value from Blynk app (0 or 1)
  digitalWrite(LED_PIN, ledState); // Set LED state
}

void setup() {
  // Initialize serial communication
  Serial.begin(115200);

  // Initialize DHT sensor
  dht.begin();

  // Initialize LCD
  lcd.init();
  lcd.backlight();
  lcd.print("Connecting WiFi");

  // Initialize LED
  pinMode(LED_PIN, OUTPUT);
  digitalWrite(LED_PIN, LOW); // Start with LED off

  // Connect to Wi-Fi and Blynk
  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);

  lcd.clear();
  lcd.print("Blynk Connected");
  delay(2000);
  lcd.clear();
}

void loop() {
  // Run Blynk
  Blynk.run();

  // Read DHT11 data
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  // Read soil moisture data
  int soilValue = analogRead(SOIL_PIN);
  int soilPercentage = map(soilValue, 4095, 0, 0, 100);

  // Check for DHT errors
  if (!isnan(temperature) && !isnan(humidity)) {
    // Display data on LCD
    lcd.setCursor(0, 0);
    lcd.print("Temp: ");
    lcd.print(temperature);
    lcd.print((char)223);
    lcd.print("C");
    lcd.setCursor(0, 1);
    lcd.print("Hum: ");
    lcd.print(humidity);
    lcd.print("%");

    // Send data to Blynk
    Blynk.virtualWrite(V0, temperature);    // Temperature
    Blynk.virtualWrite(V1, humidity);       // Humidity
    Blynk.virtualWrite(V2, soilPercentage); // Soil Moisture
  } else {
    lcd.setCursor(0, 0);
    lcd.print("Sensor Error!");
  }

  delay(2000);
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Soil: ");
  lcd.print(soilPercentage);
  lcd.print("%");
  delay(2000);
}
