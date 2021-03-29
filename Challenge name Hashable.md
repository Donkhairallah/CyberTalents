# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Hashable

In this challenge we have a welcome screen that contains posts.By inspecting elements nothing special.By pressing any post that is recently posted we get redirected to the full post page but looking in the URL there is ID to identify which post to get, by manipulating this number we don't get anything special. Let's move to the navigation bar, by pressing Hashable we get back to the welcome screen same as Home Button, In the ABOUT section nothing special there.We are left with one option which is the CONTACT section, there we have a page to input data like name, email address and message.Here we open BurpSuite to inercept traffic while we send the message.
In the Post request we have 3 params : name,email,message.While trying different injections we get a syntax error while using php code which means in the message box we can run php code. In the message we type ${system("pwd")} to get the working direcotry and we get /var/www/html/Hashable.Now let list the direcorties with ${system("ls")} we get multiple files and folders but there is one specific file which is flag\_....txt.Now we need to open this txt file wo we type ${system("cat flag filename.txt")} and we get the FLAG!
