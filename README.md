# raspi-bootstrap-weather
weather monitor on external display

TEST</br>
</br>
1: install raspbian</br>
2: sudo apt-get install epiphany-browser x11-xserver-utils xautomation unclutter</br>
3: copy startEPI.sh to home (like: ~/home/pi/.startEPI.sh)</br>
4: sudo chmod 755 /home/pi/startEPI.sh</br>
5: edit autostart:</br>
	- sudo nano ~/.config/lxsession/LXDE-pi/autostart (if you have NOOBS distribution)</br>
	- sudo nano ~/.config/lxsession/LXDE/autostart (if you have olders distribution)</br>
6: add line '@/home/pi/startEPI.sh'</br>
7: add cron's rule: sudo crontab -e</br>
8: add line '*/1 * * * * DISPLAY=:0.0 XAUTHORITY=/home/pi/.Xauthority /usr/bin/xte "key F5"'</br>
	first star is a minute (0-59), ie: */1 - refresh per every minute</br>
	more information: https://en.wikipedia.org/wiki/Cron</br>
9: sudo reboot
