# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Newsletter

In this challenge we have a box to put the email in it and press the button enter. First i tried to input regular string in it,but there is an imput format i must apply it.Looking in the elements i found input type email so i changed it to text and entered a regular string i got another imput rule wich is to use @ and . I tried using SQL injection like Select* from email @. but nothing happened i got my query like i entered it in back in the top left corner then i tried Cross site script also nothing happend, entering any string with &&@. wasn't usefull everytime i get back my string eneterd on the top left corner but when i tried whoami with backsticks  &&@. i got back www-data wich means i could use XSS method in this way using backstick. I type ls with backsticks &&@. and got list of files and directory. In the challenge description they wanted the backup filename as FLAG which end with .tar.gz 