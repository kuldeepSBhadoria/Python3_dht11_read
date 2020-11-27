# Python3_dht11_read

https://www.thegeekpub.com/236867/using-the-dht11-temperature-sensor-with-the-raspberry-pi/

Python Code for Raspberry Pi DHT11/DHT22

Next thing we need to do is install the DHT python library. This is done by entering  the following command:
sudo pip3 install Adafruit_DHT

Note: If you run into problems with the above command, you may not have PIP installed on your Pi.  You can fix that by running the following commands.  These will install PIP and other utilities you may need.
sudo apt-get install python3-dev python3-pip
sudo python3 -m pip install --upgrade pip setuptools wheel

OK. Now let’s take a look at the code we’re going to use. This is some very basic code written in Python. The first section of code imports the DHT library from Adafruit and the system time library.
import Adafruit_DHT
import time

This line defines the sensor object we will use, and the next line is a variable that defines the GPIO pin we are using.
DHT_SENSOR = Adafruit_DHT.DHT11
DHT_PIN = 4

And finally the code loop that goes next.  The “while True:” line will force everything indented after to run in an infinite loop.

First, we capture the temperature and humidity to two aptly named variables,  and then use an IF statement to check to see if it worked. If it worked, we print the temperature and humidity to the screen. If it it failed we let you know to check your wiring.

Lastly, since the DHT11 and DHT22 can only be checked a maximum of once per second, we use the system time.sleep function two pause three seconds between checks.
while True:
    humidity, temperature = Adafruit_DHT.read(DHT_SENSOR, DHT_PIN)
    if humidity is not None and temperature is not None:
        print("Temp={0:0.1f}C  Humidity={1:0.1f}%".format(temperature, humidity))
    else:
        print("Sensor failure. Check wiring.");
    time.sleep(3);
Python Code for DHT11/22 Complete

And here is the completed python code for the DHT11/22 sensors.
import Adafruit_DHT
import time
 
DHT_SENSOR = Adafruit_DHT.DHT11
DHT_PIN = 4
 
while True:
    humidity, temperature = Adafruit_DHT.read(DHT_SENSOR, DHT_PIN)
    if humidity is not None and temperature is not None:
        print("Temp={0:0.1f}C Humidity={1:0.1f}%".format(temperature, humidity))
    else:
        print("Sensor failure. Check wiring.");
    time.sleep(3);

To run your code, enter python3 mydht11.py and press enter. If you did everything correctly, you’ll start seeing the temperature and humidity reported on the terminal window every 3 seconds.
