---
tags:
- '#Customer'
---
## [[2022-10-17]]

Stock auto PC's had 1 display port and one hdmi port dual monitor setup had DVI-D and VGA. DP to DVI was used for one and HDMI to VGA adapters were ordered for the other.

- Ordered https://www.amazon.com/UGREEN-Adapter-Ultrabook-Raspberry-Chromebook/dp/B00NBUTHJG 

Holden took adapters onsite but they weren't working. Testing with technician laptop to verify adapter functionality

- Eric ran dell support assist and it connected the second monitor. Asked holden to verify that it stuck after a re-boot.
## NVR
- Camera system exists that we don't manage.
	- All cameras run into the NVR and look to be POE
	- NVR is network attached not sure if there is managment software
	- HDMI over ethernet is shooting video to another TV.
		- Adapters are currently not working. Unsure if one or both

## Time Clock
- Uattend time clock on the wall in "Server closet"


## Network

- Mapped Drives on central PC
```

C$           C:\                             Default share                      
IPC$                                         Remote IPC                         
ADMIN$       C:\WINDOWS                      Remote Admin                       
CCCAPPS      C:\CCCAPPS                                                         
EMSOUT       C:\CCCAPPS\CCC\CCCONE\EMSOUT

\\Desktop-gf0q7qp\cccapps
\\Desktop-gf0q7qp\emsout

Desktop-gf0q7qp\Owner
master

```
- No local domain
- 192.168.0.0/24
- 150/5 network speed
- ISP: Spectrum
	Static info:
		71.15.59.34
		255.255.255.248
		71.15.59.33
		dns: 71.15.59.33

## Software

