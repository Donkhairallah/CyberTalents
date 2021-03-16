# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: This is Sparta
In this Challenge we have a Login form
When pressing on Hint button we get easier than Ableton
When checking the elemnts there is a suspicious long javascript but its almost unreadable but we can see that "\_0xeb80x2" and "\_0xeb80x3" are equal the same string that has index 4 we get an alert else we get another alert wich means the username and password have the same value to get the value we copy and paste this script in javascript beautifier so we can easaly see the script.
In this script we have a function called check(). In it there is 2 variables named "\_0xeb80x2" and "\_0xeb80x3" the first one is for username and the other is for password nothing special but the we have an if else statement that tells us that if the variable == Cyber-Talents && the second variable == Cyber-Talents then Congratz else we have an alert.
Entering Cyber-Talent in username and password we get the Flag!
