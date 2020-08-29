# birdcam

## Enable SSH on your new image
Create file ```ssh```

## Connect to wifi automatically
Create ```wpa_supplicant.conf```

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
	ssid="SSID"
	psk="PASSWORD"
}
```

## Config
```sudo raspi-config```

```sudo apt update && sudo apt -y full-upgrade```

## Copy ssh keys
```
mkdir ~/.ssh
nano ~/.ssh/authorized_keys
# Paste pub key

chmod 700 ~/.ssh
chmod 644 ~/.ssh/authorized_keys
```

## Clone RPi_Cam_Web_Interface

```
git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git
cd RPi_Cam_Web_Interface
./install.sh
```

## Enable motion

```
sudo nano /etc/default/motion

# start_motion_daemon=no -> start_motion_daemon=yes

sudo service motion start
```

``` 
Videos saved to /var/www/media
```