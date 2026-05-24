Initialize ESP-NOW: Set up ESP-NOW on the ESP32-C3 to listen for incoming messages from the sender.
Process Received Data: Once data is received, process it as needed.
Forward Data: Re-transmit the received data to the next ESP-NOW device or another ESP32.
ESP32-C3 with Button (Sender)
ESP32-C3 with LED (Receiver)
Steps:

    Find MAC Addresses: Upload the code for the sender and receiver to each ESP32-C3. The sender will print its MAC address on the Serial Monitor. Use this address to set up the peer in the receiver code (replace broadcastAddress with the actual MAC address of the receiver).
    Upload and Test: Upload the sender code to the ESP32-C3 with the button and the receiver code to the ESP32-C3 with the LED.
    Button Behavior: When the button is pressed, the sender will send a message to the receiver to toggle the LED state.

This setup will toggle the LED on the receiver ESP32-C3 every time the button is pressed on the sender ESP32-C3.
I have updated the code to cope with latest changes  recent update in the ESP-NOW API that now requires an additional esp_now_recv_info structure to be passed in the callback function, instead of just the MAC address as it was done previously. The API expects a different callback signature.
