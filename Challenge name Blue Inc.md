# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Blue Inc

In this challenge we start with a welcome page, nothing special in BurpSuite. Home and About buttons nothing special in them but there is a Login page, in the challenge description they gave us credentials for demo account username and passorwd is demo. By intercepting the request while loging in wasn't usefull but when clicking on prfile and intercepting the request two times in a row and changing in cookie the user from demo to admin we where able to see the FLAG!