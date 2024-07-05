Injections vulnerabilities occurs when a user input (not only auth inputs, every input can be a vuln) is not controlled.

If a user input is not controlled, we can do some SQL injections which mean we can pass SQL command to the database through the user input

For exemple : Imagine that when we sumbit a user input for creating a nickname
the web app does something like : 
`Create in user table nickname : $user`
So if we do something like this in the input
`!! Delete * from user table`
The command executed in the db will be
`Create in user table nickname : !! Delete * from user table`
and !! = Avoid the previous command and start after these two !
Soo in this exemple we basically deleted all the users in the database.

***==Note 1 : that this exemple is totally wrong, the commands are wrong and !! means nothing in SQL 
Note 2 : There is also OS injections which allow to install reverse shell & many more==***

## Defence for injections
"*The main defence for preventing injection attacks is ensuring that user controlled input is not interpreted as queries or commands. There are different ways of doing this:*
- *Using an allow list: when input is sent to the server, this input is compared to a list of safe input or characters. If the input is marked as safe, then it is processed. Otherwise, it is rejected and the application throws an error.*
- *Stripping input: If the input contains dangerous characters, these characters are removed before they are processed.*"