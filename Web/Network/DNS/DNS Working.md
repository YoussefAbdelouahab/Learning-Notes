## How can my computer convert an url into an ip address ??

### Step 1 : Local search
My computer will look in a hosts local file, if there is any mapping ip -> domain name
My computer will also look in his DNS cache to see if it already has an ip adressed to the domain name
### Step 2 : Recursive DNS server
If any addresses hasn't already been found with the local search , a request is sent to a known server which is the recursive DNS server. this server is linked automatically to all reouters
This RDNSS will also maintain a cache for all popular addresses.

### Step 3 : Root name server
- Before 2004 there was only 13 root name DNS server in the world but not there is many more
This root name server is generally used to choose a TLD server to redirect you.
### Step 4 Top-Level Domain server (TLD server)
Top-Level domain server are dns servers split up into extensions, like there is a server for `.com` `.co.uk` `.fr` and you pc will send a request to this server if the root name don't find any addresse.

### Step 5 : Authoritative name server
This Authoritative server is used to store DNS record for domains directly.
Basically every domain in the world will have its DNS record stored into this autohoritative name server somethere or another.

# Conclusion
If your domain name is not found, until in the step 1, 2, 3, 4 it will be found in the step 4 anyways !
If not, the domain name doesn't exist !