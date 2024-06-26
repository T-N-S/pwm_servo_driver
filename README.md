# PWM Servo Driver Python Package

This package provides a Python interface for controlling servos using Pulse Width Modulation (PWM).

## Prerequisites

This library requires the `sx1509-gpio-expander` library. You can install it using pip:

```sh
pip install sx1509-gpio-expander
```

## Installation

Install the package using pip:

```sh
pip install pwm-servo-driver
```

## Usage

```python
from sx1509_gpio_expander import SX1509
from pwm_servo_driver import Servo
import board

# Configure I2C
i2c = board.I2C() 

# Create an instance of the SX1509 GPIO expander
IOExpander0 = SX1509.SX1509(i2c, 0x3F)

# Create an instance of the PWM servo driver
# The parameters are the IO expander, and the pin number for the servo
servo = Servo.Servo(IOExpander0, 1)

# Use the servo driver
# The setPosition function sets the servo angle
# Just set the angle to a value between (0-180) and the function will automatically adjust the PWM signal
servo.setPosition(90)
```

## License

This project is licensed under the GNU GENERAL PUBLIC LICENSE - see the [LICENSE](LICENSE) file for details.
