# Centralized-remotes
All remote controls on the smartphones and tablets of the family.

The Raspberry Pi Zero W works perfectly as a local web server and its Anavi Infrared PHAT (https://anavi.technology/#products) has recorded and played back the infrared signals from any brand of remote control.
A clickable and personalized web page allows to send any command or even group of commands for one or more devices by a simple click on smartphone, for example: turn on the STB then the TV and choose CNN. It couldn't be simpler and more convenient for the whole family. It has worked perfectly for 3 years.
The softwares used are classical LIRC for Anavi Infrared PHAT, Apache2 for the Web server. The main preparatory work consists in recording the infrared commands from the remote controls and then preparing the web page according to one's own needs.
The developments were made for the purposes of my own family. For any other user, the code will have to be customized according to each one's needs: different types and brands of devices, different TV providers and of course different preferences.

The first step is to prepare the Raspberry Pi with its Raspberri Pi OS as shown here: https://www.raspberrypi.org/downloads/.
It is recommended to update everything, to activate VNC Viewer, I2C and to install an FTP server as explained for example here :
https://www.raspberrypi.org/documentation/remote-access/ftp.md 

The Anavi Infrared pHAT must be installed exactly as explained here:
http://anavi.technology/files/anavi-infrared-phat.pdf
In this description, you will find out how to proceed with the next step, which is to read the useful infrared signals from each remote control, name them very carefully and without duplicates, and then save them in a single file called lircd.conf. The real example you will find here corresponds to my own hardware and must therefore be adapted according to each custom need.
Don't forget that the configuration file lirc_options.conf has to be modified to switch from recording infrared signals to transmitting them. This is explained in Setting up LIRC and Using IR LED chapters.

You can then proceed with the installation of a web server as explained here for example:
http://www.raspberryvi.org/stories/raspbian-lamp.html 
It will probably be necessary to change the default directory of the web server to /var/www and adjust the access rights to this directory.

The last step is to develop a custom web page according to your own needs. In the example given, it is structured as a table, with clickable rectangles of different colors according to their function.
Each click leads to a mini executable batch program that describes the instruction(s) to be executed.

You will find all these files and more in the appropriate folder:
- batch files in bin folder are for this directory: /usr/local/bin/ 
- lircd.conf file is for /etc/lirc/
- files in www are for this directory: /var/www/
don't forget you need to personalize them according to your own configuration.

Enjoy!

 
 
