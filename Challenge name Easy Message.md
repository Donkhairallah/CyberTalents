# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Easy Message

In this challenge we start with a login page. We start by checking the elements nothing special there same as in BurpSuite, we scan for subdomains using dirb with the command dirb http://35.240.62.111/easymessage and we get an important subdomain which is robots.txt. Adding this subdomain to the URL we get User-agent:*
Disallow: /?source 
replacing robots.txt with /?source we get a PHP code which in it there is an if statement which consist of user=specific username and password that are encoded in base64. By decoding these credentials we get username=Cyber-Talent and password=Cyber-Talent we get a morse code that we decrypt and get the FLAG!