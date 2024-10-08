RelayController Library for PCF8574
The RelayController is a Python library for controlling relays through the PCF8574 I/O expander on platforms such as the Raspberry Pi. This library allows you to easily turn on, turn off, and toggle relays using I2C communication.

Features
Turn on/off individual relays
Toggle the state of individual relays
Turn on/off all relays simultaneously
Get the current state of all relays
Installation
To use the RelayController library, you need to have Python 3.x installed on your system as well as the smbus library which enables communication with I2C devices.

You can install the smbus library using pip:

bash
Copy code
pip install smbus
Usage
First, ensure that the I2C interface is enabled on your Raspberry Pi or compatible device.

Import the library and create an instance of the RelayController class:

python
Copy code
from RelayController import RelayController

# Replace 0x20 with the I2C address of your PCF8574 module
relay_controller = RelayController(address=0x27)
Turn a relay on or off by specifying its number (1-4):


# Turn on relay 1
relay_controller.on(1)

# Turn off relay 1
relay_controller.off(1)
Toggle the state of a relay:


# Toggle relay 1
relay_controller.toggle(1)



# Turn on all relays
relay_controller.on()


# Turn off all relays
relay_controller.off()


# Get the state of the relays
state = relay_controller.get_state()
print(state)  # Outputs a binary string like '0b11110000'
Hardware Setup
Make sure that the PCF8574 is properly connected to your Raspberry Pi's I2C pins (SDA and SCL), and that your relays are connected to the PCF8574. Check the datasheet for your specific relay module to ensure proper connections.


Support
For support, please open an issue on the GitHub project page.




