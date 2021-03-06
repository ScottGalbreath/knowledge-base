---
layout: post
title:  "How to subscribe to and use the Arm lab"
categories: Labs 
author: xXraphXx
lang: en
---

Quick tutorial about the way to subscribe to the arm lab and spawn your very first aarch64 virtual machine! List of known issues with arm instances at the end.

# Spawn a virtual machine on arm

## Step 1

Go to [Runabove](https://www.runabove.com) > Labs > Discover armcloud > Start Now

![Lab](/kb/images/2015-10-13-how-to-use-arm-lab/step1.png)

![Start Lab](/kb/images/2015-10-13-how-to-use-arm-lab/step2.png)
    
## Step 2

Either sign up (create new account) or sign in (use existing account)

![Sign up/in](/kb/images/2015-10-13-how-to-use-arm-lab/step3.png)

## Step 3

Important: SSH Keys. Once logged in, you fall back on the classical runabove interface to manage your cloud objects. 
Please make sure that you have registered a public key in region **`HZ-1`** to be used to access your machine once deployed.

![SSH](/kb/images/2015-10-13-how-to-use-arm-lab/step9.png)
    
## Step 4

Create a new instance. Important: take care of choosing the correct region, flavor and image.

 * Region: arm instances are only available in region **`HZ-1`**, so make sure you select this region when spawning your server

 * Flavor: currently only one flavor available, **`vps-arm-1`**, more to be coming soon

 * Image: **`ubuntu-14.04-aarch64`**

![Launch](/kb/images/2015-10-13-how-to-use-arm-lab/step4.png)

![Region](/kb/images/2015-10-13-how-to-use-arm-lab/step5.png)

![Model](/kb/images/2015-10-13-how-to-use-arm-lab/step6.png)

![Flavor](/kb/images/2015-10-13-how-to-use-arm-lab/step7.png)

![Fire](/kb/images/2015-10-13-how-to-use-arm-lab/step8.png)


# Known issues on arm

 * If you were one of the first to subscribe to the lab, you may have entcountered poor disk and network io performances due to the kernel 3.18. The kernel 4.2 will be very soon proposed and is far better in terms of performance, so you may consider respawning a virtual machine from scratch (important: kernel upgrade directly from within the guest won't have the same effect, you won't be rescheduled at the correct place)

 * If you are using the 3.18 kernel image, you may entcounter some unstabilities concerning your instances, please forgive us for the disturbance

 * Suspend/resume -> currently not working, if your machine falls in ERROR, just shut it down and start it again. 

 * Note that as a consequence of the suspend/resume limitation above, live snapshots are not working either. please shutdown your instance before taking any snapshot (actually, under kernel 3.18, the live snapshot will work, but the machine will never resume, so you may as well shut down your instance directly...)

 * No vnc console access, but you can still get a serial console access. See this [tutorial](/kb/en/labs/how-to-serial-console-arm-instance.html)

 * When subscribing to the lab you are also presented the vps-hdd flavors (vps-hdd-\*) and images, as if you had subscribed to the vps-hdd lab. You can use them as well but this is not arm :). See [here](https://community.runabove.com/kb/en/labs/how-to-use-vps-hdd-lab.html) for more details.
