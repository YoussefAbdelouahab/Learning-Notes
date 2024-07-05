SMB for Server Message Block protocal is a client-server communication protocol used for sharing acces to files, printers & serial port or other ressources on a network

SMB = Response- request protocol
Response request protocol means that it transmit multiple messages between the client and server to establish connection (ref to TCP/IP)

What runs SMB ? 
*"Microsoft Windows operating systems since Windows 95 have included client and server SMB protocol support. Samba, an open source server that supports the SMB protocol, was released for Unix systems."*

## What tool to scan SMB

### 1 / Port scan
Basically with nmap
### 2/ [[Enum4linux]]
*"Enum4linux is a tool used to enumerate SMB shares on both Windows and Linux systems. It is basically a wrapper around the tools in the Samba package and makes it easy to quickly extract information from the target pertaining to SMB. It's already installed on the AttackBox, however if you need to install it on your own attacking machine, you can do so from the official [github](https://github.com/portcullislabs/enum4linux)."*