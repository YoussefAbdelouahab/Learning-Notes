Les DNS ne sont pas utiliser seulement pour les sites web.
Les different type de dns permette de savoir de quoi on parle.

## A record
IPv4 addreses = généralement utiliser pour les sites web.
## AAAA record
IPv6 addresses = généralement utiliser pour les sites web.

## CNAME record
Renvoie vers un autre nom de domain

	Considerons le site youssef.com et le boutique du site youssef.com étant shop.youssef.com.
	
	Si on demande le CNAME de shop.youssef.com on aura shops.shopify.com, et une autre requete DNS va etre faite a shops.shopify.com, qui celle ci va faire fonctionner l'ip

## MX Record
Gestion d'email = génralement utiliser pour de la sécuriter si un server crash.

## TXT Record 
Gestion d'un texte quelconque = généralement utiliser pour la gestion de liste de serveur et d'email.