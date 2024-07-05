Basically it is looking at the header of an email to get enough information to filter it.

In a mail header there is many technical details like :
- sender
- recipient
- path
- return address
- attachment
Usually these details are enough to know if it's a normal mail or a suspscious email 

There is two main concer : 
- Security problem : Suspcious or abnormal or malicious patterns
- performance problem : delivery and delay issues in emails

# Security issues a.k.a phishing

To understand phishing we need to understand social engineering 

Social engineering = is to use to human psychology to perform or divulging information by exploiting weaknesses in human nature. These "weaknesses" can be , curiosity, jealousy, greed, kindness, 

Phishing; phising is a sub-section of  SE (Social Engineering). it's about to trick someone into either revealing personal info or credentials, or even exec malicious code on their computer

## emlAnalyzer to analyze email & get attachment
`emlAnalyzer -i Urgent\:.eml --header --html -u --text --extract-all`
## Email reputation, basic osint
Go to Emailrep.io to see an email reputation
