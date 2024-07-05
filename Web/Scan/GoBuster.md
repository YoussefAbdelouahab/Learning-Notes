[[Scan]]
Gobuster est une commande qui permet de scanner un site web a la recherche de page internet.

On lui donne un fichier contenant des potentielle nom de page, par exemple /admin /home /dashboard etc et il va essayer chacune des url, si une existe il te la donne.

- -u : permet de spécifier le site web
- -w : permet de spécifier le fichier de word list

Exemple de commande : `gobuster -u http://fakebank.com -w wordlist.txt dir`
![[Pasted image 20240623032209.png]]