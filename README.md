# Description
Setup a DVR/Live TV Tuner in plex media server. I used a VU+ Zeor 4K<br />
The guide is what i have done in a couple of hours on a sunday evening, and not a 1:1 copy/pasta installation walktrough.
<br /><br />
Live TV in plex is a nightmare. <br />
Especillay the EPG(XMLTV) crap...

## TL;DR
- Install the VU+ Receiver
- Unwrap / put all cables in
- Flash it with [OpenVIX image](https://www.openvix.co.uk/index.php/downloads/vu-plus-images/vu-zero-4k/)
- Copy HRTunerProxy plugin to it
- Reboot device
- Configure plugin to use Bouquet
- Setup EPG fetch script
- Add tuner in plex
- Enjoy (your not so great live tv in plex)





## Installation
Do a basic setup of the STB/Receiver and proceed with the installation steps below:

### 1) Flash OpenVIX image
- Format USB Stick with FAT
- Extrag image to stick
- Power off receiver
- Put USB stick in 
- Power receiver on
- Wait for status led to flash (pulsating = flash in progress)
- Power receiver off
- Remove USB stick
- Power receiver on
- Proceed instalaltion guide

### 2) Install the HRTunerProxy Plugin
- Copy content of the `plugin` folder to `/usr/lib/enigma2/python/Plugins/SystemPlugins/HRTunerProxy` on the receiver
- Reboot the device
- Set the Bouquet you want to use in the plugin settings

### 3) Prepare plex / fetch EPG data
- Copy/Download the epg_stb.sh script to the plex server
- Edit epg_stb.cfg to match your needs
- Run the script `epg_stb.sh GET_ALL` to fetch EPG data from the Receiver

### 4) Setup the tuner in plex
- Add the tuner, if not shown, use ip/full url (`http://<ip>:6081`)
- Set the EPGXMLTV (downloaded via script above)
- Continue setup process
- Let plex finish the setup

## Links / Related information
- https://github.com/OpenViX/HRTunerProxy
- < link to `epg_stb.sh` script >
- https://www.openvix.co.uk/index.php/downloads/vu-plus-images/vu-zero-4k/
- https://meintechblog.de/2018/03/03/pimp-my-plex-dvr-live-tv-und-tv-recording-per-vu/
- https://github.com/OpenViX/HRTunerProxy/issues/55