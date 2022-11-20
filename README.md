## First steps with Jetson nano

### Update and upgrade your system:

```shell
sudo apt update
```
```shell
sudo apt upgrade
```

### Set your Python install to Python 3 Default:

```shell
sudo apt install -y python3 git python3-pip
```
```shell
sudo update-alternatives --install /usr/bin/python python $(which python2) 1
```
```shell
sudo update-alternatives --install /usr/bin/python python $(which python3) 2
```
```shell
sudo update-alternatives --config python
```

### Install Python 3.7 and Make Default:

```shell
sudo apt install -y python3.7-dev
```
```shell
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.6 1
```
```shell
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2
```
```shell
sudo update-alternatives --config python
```

### Check your python version (it should be 3.7):

```shell
python --version
```
### Run the standard updates:

```shell
sudo apt update
```
```shell
sudo apt upgrade
```
```shell
sudo pip3 install --upgrade setuptools
```

### Install nano:

```shell
sudo apt install nano
```

### I2C is enable by default.
To check that use:

```shell
sudo /opt/nvidia/jetson-io/jetson-io.py
```

### Check I2C devices with following command:

```shell
ls /dev/i2c*
```
You should see at least one I2C device

### Test to see what I2C addresses are connected by running:

```shell
sudo i2cdetect -r -y 1
```
pins 3/5
You should see adress 0x48

### Set User Permissions:

```shell
sudo groupadd -f -r gpio
```
```shell
sudo usermod -a -G gpio <username>
```

### Clone the Repo and copy the rules:

```shell
cd ~
```
```shell
git clone https://github.com/NVIDIA/jetson-gpio.git
```
```shell
sudo cp ~/jetson-gpio/lib/python/Jetson/GPIO/99-gpio.rules/etc/udev/rules.d
```

### Reboot your system:
```shell
sudo reboot
```

### Install Python Libraries:

```shell
pip3 install adafruit-blinka
```

