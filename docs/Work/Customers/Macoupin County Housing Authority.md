# Primary Contacts

-  Dionne
- Jenifer
- Amanda ? 

## Initial visit/[[Standardization]]

Manage village at Morris farms

Under new management 

Old customer new agreement, premium customer currently.

Email hosted with us

Identify printer support. History of printer issues. Figure out which ones have active support plans.

Conference room equipment has been there since 2006. They want short throw projector. Need microphone solution.

Utilize zoom for meetings.

Check Office/Licensing info

Network Stack

Backups

Domain

Email Encryption Via 
	TLS encryption triggerd via keyword "Encrypt" in subject 


## Network

- ISP
	Sparklight Buisness
		Village At Morse Farms
		1050 W Main ST
		Carlinville IL 62626
	Account# 126977578
	~314.14 monthly
	150mbps up 15 mbps down
	![[20221018_111529.jpg]]![[20221018_111551.jpg]]

- LAN
	10.0.0.0/24
	MCHA.Local
	DC: server03 
	![[20221018_111502.jpg]]
	![[20221018_111450.jpg]]

Wireless:
	MCHA
	gowireless1
	no dhcp active
	Eugeinus AP
	![[20221018_112250.jpg]]

- Network Scan![[iprange_2022-10-18_11_29_22.txt]]


- Apc xs1500 battery backup in closet. Flashing indicator says battery is dead.
	![[20221018_111510.jpg]]


## Networked Printers

- Kyocera 
	ECOSYS M2640i dw
	10.0.0.99/24
	Managed by watts
	Interview Room
	![[20221018_132331.jpg]]

-  LaserJet P4014n. 
		10.0.0.5
		Host name: NPI0D5B5A
		![[20221018_124448 1.jpg]]

Multifuction Printer 
	Watts 
		www.wattscopy.com
		18002920515
		![[20221018_110746.jpg]]

## Equipment/Software

	Servers
		1 in system
	Work Stations
		13 in system 3 offline

Yardi

Adobe Licensing Currently for 2 people
	PDF Reader - Acrobat Pro

## NVR
Reolink
	User: Admin
	Pass: Admin1.0
	![[20221018_114837.jpg]]
	![[20221018_114821.jpg]]

## Phone system managed by CDS

Panasonic Phones
	![[20221018_111241.jpg]]
	![[20221018_111443.jpg]]






## Conference room 

table has power and RJ45 that isn't connect but could be for phone/microphone devices.

	![[20221018_105121.jpg]]![[20221018_105130.jpg]]

Audio Equipment in Conference room:
	![[20221018_110326.jpg]]![[20221018_110333.jpg]]

## Computers

[AmandaK] - station6 - (FJ4K982)
	OptiPlex 3020
	Active in N-able
	Warranty Status: Expired Sat, Jun 22, 2019 07:00 PM CDT
	AV Up to date
	HP laser jet P1606vn USB attached
	![[20221018_131517.jpg]]
	![[20221018_131503.jpg]]

[Jennifer] - station4 - (7P3K982)
	  OptiPlex 3020
	  Active on N-able
	  AV up to date
	  HP Laser Jet Pro N201DW USB attached
	  ![[20221018_130410.jpg]]
	  ![[20221018_130352.jpg]]

[Dionne] - station1 - (DK4K982) 
	   OptiPlex 3020
	   Warranty Status: Expired Sat, Jun 22, 2019 07:00 PM CDT
	   Active in N-Able
	   AV Up to date
	   ![[20221018_125843.jpg]]
	   ![[20221018_125901.jpg]]

[Holly] - station8 - (6G1RDB2)
	  OptiPlex 3020
	  Warranty Info: Expired Sat, Jun 22, 2019 07:00 PM CDT
	  Active on N-Able
	  Av update
	  ![[20221018_125305.jpg]]
	  ![[20221018_125259.jpg]]

[Stephanie] - station5 - (824K982)
	OptiPlex 3020
	Warranty Info: Expired Sat, Jun 22, 2019 12:00 AM CDT
	Active on N-able
	AV up to date
	![[20221018_124254 1.jpg]]
	![[20221018_124246 1.jpg]]

[Peg] - station7 - (JH4K982)
	OptiPlex 3020
	Warranty Status:   Expired Sat, Jun 22, 2019 07:00 PM CDT
	Active on N-Able
	AV up to date
	HP LaserJet P4014n at this desk. 
		10.0.0.5
		Host name: NPI0D5B5A
	![[20221018_123705.jpg]]

[Maintenance] - STATION10 - (57Q2382)
	OptiPlex 3020
	WARRANTY STATUS: Sun, Jun 23, 2019 07:00 PM CDT
	Active on N-able
	AV Re-installed
	![[20221018_120656 1.jpg]]
	![[20221018_120846 1.jpg]]

[Dan] - station2 - (624K982)
	Dell Inc. (OptiPlex 3020)
	Active in n-able
	AV Active
	WARRANTY EXPIRY: Expired on [Sat, Jun 22, 2019 07:00 PM CDT](http://www.dell.com/support/my-support/us/en/19/product-support/servicetag/624K982)
	![[20221018_120846.jpg]]
	![[20221018_120656.jpg]]

[Conference Room] - HomeownershipCenter-PCNEW - (JJ4K982)
	Not on domain
	OptiPlex 3020
	Warranty Status Sat, Jun 22, 2019 07:00 PM CDT
	Active in N-Able

	![[20221018_104046.jpg]]

[Interview] - Station9 - (6G9RDB2)
	Optiplex 3020
	Warranty Status: Expired Sat, Jun 22, 2019 07:00 PM CDT
	Active on N-able
	![[20221018_132118.jpg]]
	![[20221018_132656.jpg]]
`
## Servers

Server03
	Server 2019
	
	![[20221018_113547.jpg]]
	![[20221018_113724.jpg]]
	![20221018_113724 1.jpg]]
	
	![[20221018_113747.jpg]]
	
	
	![[20221018_113211 1.jpg]]
	UPS's are atleast 3 years old.
		Pro 1000 has very little plugged into it 1W draw at 475m run time
		UPS 1500 90W draw ~75 min run time
	no battery errors present on these
	- Access
		- Domain : MCHA.LOCAL
		- Administrator
		- Super123$
	- Backup
		Backups through n-able on server03
		Windows server backups configured to backup daily to dedicated drive
	![[20221018_115219.jpg]]


- Server02
	![[20221018_113605.jpg]]
	Decommissioned server still on site