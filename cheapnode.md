# Run a Rocketpool node on the cheap by going used. ~$330USD #
With LEB8's around the corner and an ideal hardware solution being a NUC I thought I'd write up a cheap(er) solution for home staking hardware. I’ll go over price and performance numbers. Great for those on a budget, or for people looking for a testnet/fallback machine.


First I picked up this used MiniPC from Ebay:

![HPelitedesk800mini](/../photos/800-g32.jpg)

### **HP EliteDesk 800 G3 Mini** ### 
Review with internal photos of RAM and NVMe location [here](https://www.servethehome.com/hp-elitedesk-800-g3-mini-ce-review-project-tinyminimicro/)

System Specs:
```
Processor: 6th gen Intel i5-6500T 2.50GHz 
Cores: 4
Threads: 4
TDP: 35W 
Ram: 8GB DDR4 2400 SO-DIMM
Hard drive:NO SSD
PCIe 3.0 M.2 slot
Power adapter included
```

I found this on EBay, the seller had 50 of these units for sale. Lack of SSD makes me believe these were all from an office environment where the drives were destroyed. Carefully read any used listing to confirm that a CPU and Power adapter are included. 


Price: $69.99 + $22.96 shipping = $89.95USD


With 4 cores and 4 threads this machine will be very capable to run your rocketpool node, a TDP of 35W means it will use a small amount of power. 8GB is not the recommended amount of ram in the rocketpool docs. At a minimum an additional 8GB stick of RAM is required. Because I didn’t want to be limited in what execution client and consensus client I purchased and installed 32GB of RAM. This is also the maximum supported by the HP Elitedesk 800 G3 Mini.


CORSAIR Vengeance 32GB (2 x 16GB) 260-Pin DDR4 SO-DIMM DDR4 2400 (PC4 19200) Memory


Newegg.com Price
Price: $79.99USD


M.2 Nvme
Due to the data transfer demands of running a rocketpool node I did not cheap out in this area of the build. The Elitedesk 800 supports PCIe 3.0x so I went with:


Samsung 970 evo plus 2TB PCIe Gen 3.0 x4 NVMe 1.3
Price $159.99USD




For other suitable NVMe drives that will meet the task of home staking read [Yorrick’s guide](https://gist.github.com/yorickdowne/f3a3e79a573bf35767cd002cc977b038).


![RAM and NVMe installed](/../photos/IMG_3583.png)


After a BIOS update I installed Debian 11 (bullseye) and Rocketpool. Sync took around 30 hours and then I restored my wallet.


For a total of approximately $330.00USD This is the performance you can expect. 

![Grafana Dashboard](/../photos/elitedesk800.png)


Running Lighthouse/Nethermind:
```
IOPS Read = 109K (recommended 15k in RP documentation)
IOPS Write = 36.4K (recommended 5k in RP documentation)
CPU load averaging under 40%
Measured Avg Power over 24hr period: 13.05W 
RAM usage is 22GB (note: running nethermind)
CPU Temperature under 40C
NVMe Temperature mid 40’s
SSD Latency under 6ms
I/O Wait time under 45ms 
```

Add NVMe Temp to your gradana following this [guide by Patches](https://gist.github.com/jshufro/65160a680076224d0294d1d6f1a0fa97)




Other considerations: Used miniPCs like this one may have been run 24/7 for years on end so I blew it out with compressed air, applied new thermal paste to the CPU. During initial sync the NVMe temps spiked to the mid 70’s C for a day and a half so I also added a cheap NVMe heatsink.

Trevorn.eth
