PiRSClock-Basic
==============

PiRSClock-Basic is a Raspberry Pi Radio Studio Clock written in python using pygame. It will display a clock in full screen on most monitors, displays and TVs.

This was designed specifically for the Raspberry Pi but can be used with most computers with Linux installed. Future versions (which will be in a different repository) will include indicators for microphones, telephones etc... for use in a radio studio.

## Development Status

***

PiRSClock-Basic is currently stable and ready for use.

## Installation for Raspberry Pi

***

It's recommended to use Debian Wheezy or above for this project and a 4GB or more SD Card.
For reliability I recommend to only use this Pi for the clock.

Note: The Pi will have the most accuracy in time keeping when it has a constant connection to the internet.

Once you have copied the Debian Wheezy Image to your SD Card and booted your Pi for the first time, a prompt will come up called:
    
    Raspberry Pi Software Configuration Tool (raspi-config)

You need to select:

    1 Expand Filesystem
Then

    <Ok>

Next we need to:

    3 Enable Boot to Desktop/Scratch

and select:

    Console Text console

**THIS PART IS IMPORTANT TO GET THE RIGHT TIMEZOME**

Select:

    4 Internationalisation Options

Then:

    I2 Change Time Zone

You will have a list of continents/geographical areas, select your one. Then select a region or city in your time zone.

When you are done select:

    <Finish>
    
Then Reboot.

Once you have rebooted and logged in lets make sure everything is up to date:

    sudo apt-get update
    
Then

    sudo apt-get upgrade
    
Now we need to get setuptools:

    sudo apt-get install python-setuptools
    
And finally we install PiRSClock-Basic:

    sudo easy_install PiRSClock-Basic
    
and there we have it!

## Running it

***

All we have to do is:

    pirsclockbasic
    
To quit just hold down keys Q and T at the same time.

## Making it startup automatically when you plug in the Pi

***

Firstly:

    sudo crontab -e
    
And add this to the bottom of the file:

    @reboot /usr/local/bin/pirsclockbasic &
    
Press Ctrl and O keys together to save.

Then press Enter.

Then Ctrl and X to exit

    sudo reboot
    
To test it.
    
It should now automatically display after you reboot and every time you turn it on. Remember hold Q and T to get back to the command line if needed.
