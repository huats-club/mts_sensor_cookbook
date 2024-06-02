# Piezo Sensor

## Sample Code
```
import RPi.GPIO as GPIO
import time

# Set up the GPIO pin
sensor_pin = 17
GPIO.setmode(GPIO.BCM)
GPIO.setup(sensor_pin, GPIO.IN)

def main():
    try:
        while True:
            # Read the sensor value
            sensor_value = GPIO.input(sensor_pin)
            if sensor_value == GPIO.HIGH:
                print("Vibration Detected")
            else:
                print("No Vibration")
            time.sleep(0.01)
    except KeyboardInterrupt:
        GPIO.cleanup()

if __name__ == "__main__":
    main()
```