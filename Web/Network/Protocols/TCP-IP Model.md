Contrairement au model OSI, qui n'est principalement que fictif, le model TCP/IP est lui utiliser irl.
Il contient lui aussi ces couches, 4, et c'est sensisblement la meme chose que l'OSI il y a juste des couches qui sont regroupé.
![[Pasted image 20240618172834.png]]

## TCP?, IP?
TCP viens de la suite de protocol du schéma ci dessus, et qui veux dire (transmission control protocol) et IP vien de Internet Protocol et c'est ce qui control comment les packets obtiennent leurs adresses et sont envoyer
# Connection-based protocol

TCP/IP est un protocol qui nécéssite une connection. 
Cela signifie qu'avant d'nevoyer la donner le protocol a besoin d'une connexion stable entre les deux machines.
## Comment ça fonctionne pour avoir une connection

La connexion se base sur 3 étapes important. la Syn request, Syn/Ack request et Ack request.

![[Pasted image 20240620002122.png]]
### Syn request
La machine envoie une requete spécial contenant quelque chose qui s'appelle SYN bit, qui généralement commence le processus de connexion.
### Syn / Ack
Suite à la première requete, le server va répondre avec un paquet contenant le syn bit, mais aussi un autre "Acknowlegdement" bit appeler Ack.
### Ack
Et pour terminer la première machine va renvoyer une requete avec seulement le Ack bit, ce qui va confirmer la connexion avec succes.

Ce processus se nomme "the Three-way handshake" ^f69e34