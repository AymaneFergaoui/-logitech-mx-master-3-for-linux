# -logitech-mx-master-3-for-linux
My /etc/logid.cfg File


The Logitech Options program isn't available for Linux, but by a nice guy on GitHub ([PixlOne](https://github.com/PixlOne)) created an open source project that lets you obtain some of that functionality. It's called [logiops](https://github.com/PixlOne/logiops). It works in conjunction with the [Solaar](https://github.com/pwr-Solaar/Solaar) project as well, which I find especially handy since that shows your available battery life in the system tray and lets you pair/unpair devices with the Logitech Unifying Receiver.

Here are some additional pages with info that I used to generate this documentation:

- <https://github.com/PixlOne/logiops/wiki/Configuration>
- <https://github.com/PixlOne/logiops/blob/master/logid.example.cfg>
- <https://github.com/torvalds/linux/blob/master/include/uapi/linux/input-event-codes.h>
- <https://wiki.archlinux.org/index.php/Logitech_MX_Master>
- <https://www.logitech.com/en-us/products/mice/mx-master-3.910-005620.html>

## Installation

Installation instructions for different distributions are available from the developer, but here are the commands for an Ubuntu workstation (I've verified it works with 20.04, 21.10, and 22.04):

```bash
sudo apt install -y cmake libevdev-dev libudev-dev libconfig++-dev
git clone https://github.com/PixlOne/logiops
cd logiops
mkdir build
cd build
cmake ..
make
sudo make install
sudo touch /etc/logid.cfg
sudo systemctl enable --now logid
```
