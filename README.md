# headsetcontrol-notificationd

**Fork from https://gitlab.com/devnore/headsetcontrol-notificationd all credits to him**

I only changed service name to make it equal to README.md one, fixed `Disconnected` event for my headset and add my
preferences when the headset connects.

![screenshot](https://screenshot.tbspace.de/jpcefkgwhvy.png)

headsetcontrol-notificationd is a small daemon that polls headsetcontrol to display notifications about the charge status of several headsets.
For a list of supported devices please check [Sapd/HeadsetControl](https://github.com/Sapd/HeadsetControl).

### "Design"
headsetcontrol-notificationd is a rewrite of (https://github.com/Manawyrm/headsetcontrol-notificationd) replacing php with pure bash,

### Requirements
bash, HeadsetControl and notify-send

on Arch: `headsetcontrol` (AUR), `bash` (core) and `libnotify` (extra)

You will also need a notification daemon if you are not using a desktop environment.

### Installation
```
git clone https://gitlab.com/devnore/headsetcontrol-notificationd.git
cd headsetcontrol-notificationd

sudo cp headsetcontrol-notificationd.service /etc/systemd/user/headsetcontrol-notificationd.service
sudo cp headsetcontrol-notificationd /usr/local/bin/headsetcontrol-notificationd
sudo chmod +x /usr/local/bin/headsetcontrol-notificationd

sudo systemctl daemon-reload
systemctl --user enable --now headsetcontrol-notificationd
```
