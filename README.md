# VNC-Server-Jetson-Nano
Setting up a VNC server for the jetson nano to control directly from a PC instead of the jetson nano.

# JETSON NANO and Computer need to be on the same network.

ON JETSON NANO:
1. Enable VNC server each time you log in
'''
mkdir -p ~/.config/autostart
cp /usr/share/applications/vino-server.desktop ~/.config/autostart/.
'''

2. Configure VNC Server
'''
gsettings set org.gnome.Vino prompt-enabled false
gsettings set org.gnome.Vino require-encryption false
'''

3. Set password to VNC Server
'''
gsettings set org.gnome.Vino authentication-methods "['vnc']"
gsettings set org.gnome.Vino vnc-password $(echo -n 'thepassword'|base64)
'''

4. Reboot
'''
sudo reboot
'''

On another Computer:

1. [Download and Install VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)
2. Launch VNC Viewer and type in IP address of Jetson Nano
3. Provide password if needed.
