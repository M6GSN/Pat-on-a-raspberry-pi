# Pat on a Raspberry Pi with GPS
how to install and configure pat the Linux winlink client

I will be doing this on a Raspberry Pi 3 Model B Rev 1.2

___

Ingredients.

Raspberry Pi 3 4 or zero w

Case for the Pi

a USB lead to power the Pi

if you are using a Pi zero then you will need a USB OTG adaptor

Lastly a power supply this can be a wall adaptor or a power bank if you are using a PI 4 make sure the power bank is a PD compatible unit


Firstly we will update and upgrade the Raspberry Pi OS by running the following command line `sudo apt update && sudo apt full-upgrade -y`

once this is done we need to install gpsd the service daemon that we will use to get GPS date to pat  the command we will be using will also give us tools to test that all is configured correctly just run the following command `sudo apt install gpsd-clients -y`