[[Scan]]
Nmap sert générallement a scanner different type de port.

## Fonctionnement ?
Nmap va se connecter a chacun des port d'une machine de manière consécutive.
Dépendamment de comment le port répond, il sera déterminer si le port est ouvert ou fermé.
	PS: Partant du principe que chaque pc contient 65535 port, il vaut mieux éviter de tout scanner.
De 0 a 1024, les ports sont "well-known", scanner au dela n'est peut-etre pas intéréssant.

## Usefull Scan types
Les options principales a utilisé sont : `-sT, -sS, -sU` 
-sT = TCP connect Scans ->[[TCP-IP Model#^f69e34 | Three way handshake]] with each target port in turn
-sS = SYN "Half-open" Scans
-sU = UDP Scans
### Some more ?
les options de deuxième recours a utilisé sont : `-sN, -sF, -sX`
-sN = TCP Null Scans
-sF = TCP FIN Scans
-sX = TCP Xmas Scans

---
## -sT TCP
The -sT scan work with the [[TCP-IP Model]] which means a [[TCP-IP Model#^f69e34 |Three way handshake]] will be tried with each target port in turn.
### Closed
Your pc will send a Syn request and if the port is closed the target server will respond with a TCP packet with the RST (Reset) flag, which means the port is closed
### Open
If the port is open the target server will respond with a SYN/ACK flag which mean the port is open and finish the handshake by sending back a request with the ACK flag
### Open but hidden behind a firewall ? (Filtered)
Many firewall can simply **drop** incomming packet , nmap sends a TCP SYN request and receives nothing back. tha means the port is being protected by a firewall and nmap return filtered

---
## -sS SYN
In SYN Scan, nmap tried a three way handshake, but when the second step is done, nmap return a RST packet.
it has many advantage like : 
- bypass older intrusive which look for a simple three way handshake
- Syn scan is not logged, because it don't perform a full connexion
- Syn scan don't have to disconnect or complet any connexion so it's way more faster
But is also have some disadvantages like :
- Require sudo permission
- Unstable service can be get down by Syn scan, which can be problematic

SYN scan is basically the scan used by nmap automatically when used under root privileges
![[Pasted image 20240620172406.png]]

---

## -sU UDP
Unlike TCP, UDP connections are _stateless_.
## Open
*When a packet is sent to an open UDP port, there should be no response. When this happens, Nmap refers to the port as being `open|filtered`. In other words, it suspects that the port is open, but it could be firewalled. If it gets a UDP response (which is very unusual), then the port is marked as open. More commonly there is no response, in which case the request is sent a second time as a double-check. If there is still no response then the port is marked open|filtered and Nmap moves on.*

UDP scan is very long, it's arround 20 min to scan the first 1000 port because it's hard to know if the port is really open or filtered 
to bypass that we loose a scan with --top-ports 
for exemple : nmap -sU --top-ports 20 target
it will scan the top 20 most commonly used udp port.

---
# Ping Sweep -sn
Ping sweep is used to know which ip adresses contain active hosts, so machine turned on.
It mean that nmap will send an ICMP packet ([[Ping]]) to each possible ip of the specified network.
if nmap receives a response it mark the ip adress as being alive

exemple : nmap -sn 192.168.1.0/24
![[Pasted image 20240620181303.png]]

---

# NSE Script
The Nmap Script Engine (NSE) is like a pluggin to nmap which allow us to use so many more hacking functionnalities like using vulnerabilities or exploit.
NSE has been coded in lua programming language, and can be used to do various things.

Can use nse a script with nmap by using the switch --script
more basically to choose a category of the script we can use nmap --script=safe
to run a specific script it's the same --script=script name for exemple --script=http-fileupload-exploiter.

[NSE DOC](https://nmap.org/nsedoc/) -> full list of different scripts 

---
## -Pn
it tell to nmap to not ping the host before scanning it.
it permit us to bypasse firwall icmp blocker by considering the host as always on.

the disadvantage is that it can be very long cause if the host is effectively down, nmap will still check and double check  on the ports

[Link of the nmap doc for firewall evasion](https://nmap.org/book/man-bypass-firewalls-ids.html)

## Some more
![[Pasted image 20240620183646.png]]