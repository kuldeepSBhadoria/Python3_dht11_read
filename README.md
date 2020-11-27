# Python3_dht11_read

https://www.thegeekpub.com/236867/using-the-dht11-temperature-sensor-with-the-raspberry-pi/

Python Code for Raspberry Pi DHT11/DHT22

Next thing we need to do is install the DHT python library. This is done by entering  the following command:
sudo pip3 install Adafruit_DHT

Note: If you run into problems with the above command, you may not have PIP installed on your Pi.  You can fix that by running the following commands.  These will install PIP and other utilities you may need.
sudo apt-get install python3-dev python3-pip
sudo python3 -m pip install --upgrade pip setuptools wheel

To run your code, enter python3 mydht11.py and press enter. If you did everything correctly, you’ll start seeing the temperature and humidity reported on the terminal window every 3 seconds.
