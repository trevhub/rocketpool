# Protecting your Rocketpool node from power outages on the cheap #

An uninterruptible power supply (UPS) is a device that allows a computer to keep running for at least a short time when incoming power is interrupted. Along with a power connection, through a secondary USB connection to your staking machine can trigger a **graceful shutdown** in the event of a power loss. Without this in place, a **hard shutdown** can cause corruption of program and operating system files causing the need to re-sync your Execution Layer (ETH1) or Consensus Layer (ETH2) client. With Ice storms, hurricanes, and terrible power utility infrastructure I wanted to protect against these events the cheapest way possible. My goal wasn’t to stay up with battery power for any meaningful length of time, just to gracefully shut down my staking machine, then when power is restored automatically start it and continue attesting on the ethereum network. Total hands-of worry free operation.

Most staking machines use under 25W of power so the load requirements are pretty low. I looked for the cheapest UPS with the USB connectivity needed for a graceful shutdown command to a PC.

## Cyberpower CP425SLG ## 
### MSRP: $57.95USD ###
![CP425SLG](/../photos/CP425SLG_F2.jpg)
Specs:
```
Capacity: 425 VA / 255 W
Topology: Standby
Waveform: Simulated Sine Wave
Output: 120 VAC ± 5%
Plug type & cord: NEMA 5-15P, 5 ft. cord
Outlet types: 8 × NEMA 5-15R
Communication ports: USB
Management software: PowerPanel® Personal
Warranty: 3 year
Connected Equipment Guarantee: $75,000
```
A 255W capacity is more than enough for my 
```
staking machine (13W) 
fiber modem (25W) 
router (10W) 
= 48W
```
48W works out to 19% load on the CP425SLG and will give me 36 minutes of uptime. ([or 8% Load 3h 13 minutes on the $599 APC SMC1500C](https://www.apc.com/us/en/product/SMC1500C/apc-smartups-c-line-interactive-1440va-tower-120v-8x-nema-515r-outlets-smartconnect-port-usb-and-serial-communication-avr-graphic-lcd/))

The connections:
![ups connections](/../photos/UPSconnections.png)
The left side of the CP425SLG is for surge protection and doesnt run on battery power during an outage, I have my TV, Stereo, Laptop plugged in to those outlets. 

## **Installing the Cyberpower software on your node:** ##

There are two options for UPS management in linux. **[Cyberpowers PowerPanel](https://www.cyberpowersystems.com/product/software/power-panel-personal/powerpanel-for-linux/)** to configure and monitor your UPS or **[Network UPS Tools](https://networkupstools.org/)**. A free and open source UPS program licensed under the terms of GNU Public License (GPL). NUT works with 170 different manufacturers, and several thousands of models.

*Security Note: you are about to install software on your staking machine, always independently verify.*

I went with Cyberpowers Powerpanel.
https://www.cyberpowersystems.com/product/software/power-panel-personal/powerpanel-for-linux/

choose your install file.
![powerpanel](/../photos/powerpanel.png)

Log into your node and download the `*deb` file replacing `[CORRECT URL]` with the address

`curl -O https://[CORRECT URL]/PPL_64bit_v1.4.1.deb)`

Install replacing [PATH] with the location of the downloaded .deb file.

`sudo dpkg -i [PATH]/PPL_64bit_v1.4.1.deb`

connect the USB cable from UPS to your node. `sudo pwrstat -status` Should show an output like this. 

[pwrstat](/../photos/Screenshot from 2023-02-04 16-12-42.png)

