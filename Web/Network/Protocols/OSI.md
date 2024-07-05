![[Pasted image 20240618161258.png]]

OSI = Open Systems Interconnection
l'OSI est un moyen de théoriser la discussion entre machines via le réseau (je trouve vraiment pas plus simple pour le décrire) ==c'est le moyen de comprendre comment ça ce fait que deux machine puisse s'envoyer des données==

l'OSI est consistué de plusieurs couches (Application , présensation, session, transport , network, data link, physical)

Chaque donnée qui doit etre envoyer via le réseau passe par ce systeme.

1. Application : Récupère la data depuis quelque part 👀
	
	2. Présentation : Transforme la donnée pour lui donner un format standard (Encrypted, compresed, ...)	
	
	3. Session : Crée & | recherche une connexion entre les deux machines
	
	4. Transport : Choisis le type de transport protocole ([[TCP-IP Model]](la data deviens un segment) ou UDP(la data deviens un datagram))
	 
	5. Network : Localise la destination de la requete, généralement via l'utilisation de l'adresse ip
	 
	6. Data Link : Vérrifie qu'il n'y a eu aucune perte de donnée, ou donnée corrompue, puis format la donnée pour lui ajouter l'adresse physique de la machine destinataire (MAC)
	 
	7. Physical : Ici on parle de l'hardware c'est le composant physique dans la machine qui va envoyer l'impulsion éléctrique dans le réseau
	 
---

## Encapsulation et de-encapsulation

![[Pasted image 20240618163701.png]]

### Encapsulation
Pendant que la data passe par les différentes couches du system OSI, on y ajoute a chaque étape des détails spécifique de la couche ou on se trouve, ce principe se nomme l'encapsulation.

Par exemple : la couche network ajoute dans la donnée un header contenant la destination ip address

Par exemple : la couche Transport ajoute un headers contenant l'information du protocole de transport choisis (PCI ou UDP)

### De-encapsulation
Une fois la data reçu sur la machine de destination, il ne reste plus qu'a refaire les étape dans le sens inverse , ce principe se nomme la de-encapsulation.

On pourrait croire que toutes les machine utilise le systeme OSI, pour envoyer et recevoir des donnée, mais in fact c'est pas aussi simple, parcontre toutes les machines utilise bien le principe d'encapsulation et de-encapsulation.

*"The processes of encapsulation and de-encapsulation are very important -- not least because of their practical use, but also because they give us a standardised method for sending data. This means that all transmissions will consistently follow the same methodology, allowing any network enabled device to send a request to any other reachable device and be sure that it will be understood -- regardless of whether they are from the same manufacturer; use the same operating system; or any other factors."*