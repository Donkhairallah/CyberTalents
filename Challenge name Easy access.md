# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Easy access

In this Challenge we have a login page.
Nothing special in the elements or BurpSuite.Forgot your Password? doens't work, lets try sql injection method.First type in the username: admin' and anything in password. We get an Error mentioning MariaDB.In the password section there is a script that convert the password from plain text to md5 hash, but the first character is ' and in the end there is no single quote which means we need to close it. Now write in the username Admin' OR '1'='1' ' and anything in password .The last single quote is to close the password input. In this case we don't need to comment password section in the query if we need to do so we simply add --. Now you have the FLAG!
