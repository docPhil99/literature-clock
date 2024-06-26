# literature-clock
Clock using time quotes from the literature, based on work and idea by
        [Jaap Meijers](http://www.eerlijkemedia.nl/) ([E-reader clock](https://www.instructables.com/id/Literary-Clock-Made-From-E-reader/)) and the web version by [JohannesNE](https://github.com/JohannesNE/literature-clock).

This fork runs on python using PyQt5 and is designed for the for using the Raspberry Pi 7" touch screen.

**Note that some of the quotes are NSFW.** I'm working on a fix.

## Install

On the Raspberry pi

`sudo apt install python-pyqt5`

download or clone the this repo and run `python pi_clock.py` for the downloads directory

![imgage of Raspberry pi](https://user-images.githubusercontent.com/11662863/44579489-78485100-a78e-11e8-88b5-2a9f23b51aae.JPG)

## Usage

The app runs full screen and is designed for an 800x480 display. To quit, press/click anywhere to bring up the quit button.

There's also a `lit_clock.desktop` file. You can edit the paths in the file for your system, copy it into `~./Desktop` if you want to start the app from the desktop.

### Autostarting at boot
`chmod u+x pi_clock.py`

Then add `@/home/pi/python/literature-clock/pi_clock.py` to the end of the file `~/.config/lxsession/LXDE-pi/autostart`

You'll need to edit the path depending on where you have downloaded the files to.

### Starting the app via SSH.

If you SSH into your pi like I do, by default the clock runs on my mac rather than the pi. Change the display settings:
```
export DISPLAY=:0
nohup python pi_clock.py &
```
The `nohup` detaches the process from the terminal so you can log out and leave the app running.

Or from your remote computer 
`ssh pi@192.168.2.4 'export DISPLAY=:0; cd /home/pi/python/literature-clock;nohup python pi_clock.py >foo.out 2> foo.err </dev/null &'` (edit IP address and file path as needed)

