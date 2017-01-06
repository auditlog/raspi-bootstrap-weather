# raspi-bootstrap-weather
weather monitor on external display

1: install raspbian
2: sudo apt-get install epiphany-browser x11-xserver-utils xautomation unclutter
3: copy startEPI.sh to home (like: ~/home/pi/.startEPI.sh)
4: sudo chmod 755 /home/pi/startEPI.sh
5: edit autostart:
	- sudo nano ~/.config/lxsession/LXDE-pi/autostart (if you have NOOBS distribution)
	- sudo nano ~/.config/lxsession/LXDE/autostart (if you have olders distribution)
6: add line '@/home/pi/startEPI.sh'
7: add cron's rule: sudo crontab -e
8: add line '*/1 * * * * DISPLAY=:0.0 XAUTHORITY=/home/pi/.Xauthority /usr/bin/xte "key F5"'
	first star is a minute (0-59), ie: */1 - refresh per every minute
	more information: https://en.wikipedia.org/wiki/Cron
9: sudo reboot
