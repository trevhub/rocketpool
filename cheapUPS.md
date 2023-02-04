# Protecting your Rocketpool node from power outages on the cheap #

An uninterruptible power supply (UPS) is a device that allows a computer to keep running for at least a short time when incoming power is interrupted. Along with a power connection, through a secondary USB connection to your staking machine can trigger a **graceful shutdown** in the event of a power loss. Without this in place, a **hard shutdown** can cause corruption of program and operating system files causing the need to re-sync your Execution Layer (ETH1) or Consensus Layer (ETH2) client. With Ice storms, hurricanes, and terrible power utility infrastructure I wanted to protect against these events the cheapest way possible. My goal wasn’t to stay up with battery power for any meaningful length of time, just to gracefully shut down my staking machine, then when power is restored automatically start it and continue attesting on the ethereum network. Total hands-of worry free operation.

Most staking machines use under 25W of power so the load requirements are pretty low. I looked for the cheapest UPS with the USB connectivity needed for a graceful shutdown command to a PC.

## Cyberpower CP425SLG ## 
### MSRP: $57.95USD ###

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
A 255W capacity is more than enough for my staking machine (13W), cable modem (25W) and router (10W). 
