---
title: "Install Windows on Linux"
date: 2022-01-02
categories: ["Linux"]
type: "post"
url : "/guides/windows-on-linux/"
showtableOfContents: true
description: "Install Windows on your Linux system with our step-by-step guide. Learn how to use virtualization software and run Windows applications seamlessly on Linux."
---

# Brief

Some things just are better on windows than linux thus having a windows virtual machine(VM) is a great idea specially when daily driving linux.

We will be using Vert Manager to use windows 7 on vanilla Debian linux however, this will work on any Debian based system i.e Ubuntu.

Machine I am using:
![Machine ScreenShot](/img/guides/2022/windows7onlinux/machine-windows7Linux.png)

## Step 1: Confirm virtualization

Open terminal and type 
```
grep -o "vm\|sum" /proc/cpuinfo
```

![Output ScreenShot](/img/guides/2022/windows7onlinux/virtualization-confirmation.png)

here the command outputs ‘vmx’ but if u are not using intel processor it will show ‘SVM’ instead. If it doesn’t show anything that means virtualization is not enabled. (search for your make and model and how to enable virtualization in this case since the BIOS menu looks different for every system).

## Step 2: Downloading

Start downloading [Windows 7](https://bit.ly/2R8XFXO)
Next, install qemu-kvm and its dependencies
```
sudo apt install qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils libguestfs-tools genisoimage virtinst libosinfo-bin virt-manager -y
```
then run
```
sudo adduser $USER libvirt && sudo adduser $USER libvirt-qemu
```
This command adds user to KVM group

![ScreenShot of command output](/img/guides/2022/windows7onlinux/KVM-group.png)

## Step 3: Installation

1. Open Virt Manager

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing1.png)
2. Go to file -> New Virtual Machine

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing2.png)
3. Choose "Local install media (ISO image or CDROM)"

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing3.png)
4. Browse to your iso file

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing4.png)

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing5.png)

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing6.png)

5. In memory give at least half of the host system resources

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing7.png)
6. Here go with the default options

    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing8.png)

7. Here u can change the name of your VM, i am going with win7
    ![screenshot of the step](/img/guides/2022/windows7onlinux/installing9.png)
    
8. Run the Virtual Machine & go with OS install process.

that’s it ✌🏽

-------------------------------------------------------------
{{< rawhtml >}} 
 
{{< /rawhtml >}}