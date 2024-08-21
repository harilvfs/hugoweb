---
title: "Fedora Post-Install Guide"
date: 2023-02-03
categories: [Linux]
url : "/guides/fedora-post-install-guide/"
type: "post"
showtableOfContents: true
description: "Optimize your Fedora distribution with our post-installation guide. Follow our tips to maximize your experience."
---

## Speed up DNF 
add/edit the following file `/etc/dnf/dnf.conf`
```
fastestmirror=True
max_parallel_downloads=10
defaultyes=True
keepcache=True
```
To clean the cache: `dnf clean all`

## System Update
```
sudo dnf update && sudo dnf upgrade -y && sudo reboot
```

## Enable RPM Fusion
```
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
``` 

For any errors or other installation guide, visit [rpmfusion.org](https://rpmfusion.org/Configuration)

## Enable Flatpaks 
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Install Media Codecs 
```
sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
sudo dnf groupupdate sound-and-video
```

## Install GNOME applications 
Install GNOME Tweaks: 


that's it <3

----

  