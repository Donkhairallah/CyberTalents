# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Encrypted Database

In this challenge we start with a welcome screen.
Start with inspecting the buttons Home/About/News/Contact US nothing special no login form or anything special. Intercepting the traffic with BurpSuite wasn't usefull. While inspecting the element there is an important script which have a path in it secre-admin/assets/app.js which mean there is directories in the current directory. By putting this in the URL it wasn't usefull we got a long JQuery so lets try putting every single part alone.We start by adding secret-admin in the URL and we got a login page. Intercepting the login request wasn't usefull,but inspecting the element was.The challenge name is encrypted database which mean our target is the database. In the elements there is an input field that's hidden type and it's name is db and the value is hidden-database/db.json.
By copying this path and paste it in the URL we end up with the FLAG!
