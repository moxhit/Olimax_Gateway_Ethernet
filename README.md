# Ethernet Event Handling with ESP32

This project demonstrates the usage of Ethernet events with the ESP32. It uses the Ethernet library to handle Ethernet events such as connection, disconnection, and IP acquisition. The project also includes a simple test client to connect to a remote server and fetch data.

## Components Used
- ESP32 Development Board
- Ethernet PHY Module (e.g., LAN8720)
- Ethernet Cable

## Hardware Setup
1. **ESP32 to Ethernet PHY Module:**
   - **ETH_PHY_MDC** to GPIO 23
   - **ETH_PHY_MDIO** to GPIO 18
   - **ETH_PHY_POWER** to GPIO 5
   - **ETH_CLK_MODE** to GPIO 0 (Clock Input)
   - **ETH_PHY_ADDR** to 0 (default)
   
   Adjust the GPIO pins as necessary based on your specific hardware configuration.

## Software Setup
1. **Libraries Required:**
   - `ETH.h` - Ethernet library for ESP32.

2. **Installation:**
   - Ensure you have the ESP32 board support package installed in the Arduino IDE.
   - Install the `ETH` library through the Library Manager or manually include it in your project.

3. **Code Overview:**
   - **Event Handling:** The `onEvent` function handles various Ethernet events such as start, connection, IP acquisition, disconnection, and stop. It updates the `eth_connected` flag based on the event.
   - **Network Test:** The `testClient` function connects to a specified host and port, sends an HTTP GET request, and prints the response to the Serial Monitor.
   - **Setup and Loop:** In the `setup` function, Ethernet is initialized and event handling is set up. The `loop` function periodically tests the network connection by connecting to `google.com` and retrieving data if Ethernet is connected.

4. **Usage:**
   - Upload the code to your ESP32 board.
   - Open the Serial Monitor to view Ethernet events and network connection status.
   - The ESP32 will attempt to connect to `google.com` every 10 seconds and print the HTTP response.

## Notes
- Make sure the Ethernet PHY module is properly connected and powered.
- Adjust GPIO pins and PHY settings as per your specific hardware configuration.
- The code uses a simple HTTP GET request for demonstration purposes. For more complex interactions, modify the `testClient` function accordingly.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

