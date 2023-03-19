[]{#anchor}Pat on a Raspberry Pi with GPS
=========================================

how to install and configure pat the Linux winlink client

I will be doing this on a Raspberry Pi 3 Model B Rev 1.2

Ingredients.

Raspberry Pi 3 4 or zero w

Case for the Pi

a USB lead to power the Pi

if you are using a Pi zero then you will need a USB OTG adapter

Lastly a power supply this can be a wall adapter or a power bank if you
are using a PI 4 make sure the power bank is a PD compatible unit

Method

installing software

Firstly we will update and upgrade the Raspberry Pi OS by running the
following command line *sudo apt update && sudo apt full-upgrade -y*

Once this is done we need to install gpsd the service daemon that we
will use to get GPS date to pat the command we will be using will also
give us tools to test that all is configured correctly just run the
following command *sudo apt install gpsd-clients -y*

now we need to install [pat](https://getpat.io/) at time of writing the
latest version is v0.13.1 to get and install this we need to run the
following command line *wget
https://github.com/la5nta/pat/releases/download/v0.13.1/pat\_0.13.1\_linux\_armhf.deb*
then run *sudo dpkg -i pat\_0.13.1\_linux\_armhf.deb -y*

Now to configure the system

first of configure the GPS. First with out the GPS plugged in run *ls
/dev/tty???0* note there should be a entry and that ls /dev/ttyAMA0 now
plug in your GPS unit and re run the above command again you should see
in addition the the ttyAMA0 ether ttyUSB0 or TTYacm0 note what it is and
then run the following commands

*cd /etc/default/*

*sudo rm gpsd*

*wget
https://raw.githubusercontent.com/M6GSN/Pat-on-a-raspberry-pi/main/gpsd*

*sudo nano gpsd*

here we need to edit one of two lines both staring \#DEVICES depends on
how your GPS unit shows up we need to remove the \# from that one and
remove the other line when done press Ctrl+s then Ctrl+x.

Testing GPS. First off reboot the system this is so our changes to the
GPSD file can take hold in the system to reboot your pi run *sudo
reboot* When your Pi reboot we will test that the GPS is configured
properly by running *cgps* if all is working you should see GPS
including your grid reference and should look like the image below but
with moving text

![](Pictures/100000000000050000000320DDAB7FFC28D204D3.png){width="45.156cm"
height="28.222cm"}

cgps running all good