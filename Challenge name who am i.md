# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: who am i ?

In this Challenge we have a login page. While inspecting the elements there is a guest credentials which is username and password= Guest. Lets turn on BurpSuite to intercept the request before sending it and send the request we got access denied comeback with admin priviliges, by reloading the request there is an authentication code in the cookie which is base64 format, The result of decoding it is login=Guest7  lets try to change it to login=admin and encoded in base64 and put it in the authentication part, and we obtain the FLAG! 