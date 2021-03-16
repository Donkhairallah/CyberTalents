# CyberTalents
 Cybertalents challenges write-ups
 Web-Security: 
 
 Challenge name: Join Team
      First we check "Inspect Elements" nothing suspicious everything looks normal on home page
        Then Check the Home button , About button and our great button but nothing unusual 
        But in the WorkForUs they ask us to submit the CV .
        Lets fireup BurpSuite to intercept the traffic before sending anything and connecting our proxy to the web.
        First i tried sending a .txt file but we ended up with "Only PDF Document Allowed", Which means there is a secuirty measures on the type of file uploaded.
        So i create a .php file and wrote in it:
        <?php
        echo 'test'
        ?>
        Using the BurpSuite we were able to manipulate the file type, So i changed the filename from .pdf to .php and in the content-type to "application/pdf" and forwarded it
        In BurpSuite in the proxy section go to HTTP history and press on the last request we forwarded it we can see in the Response part we can see that there is a location code data/filename.pdf>
        By changing the URL from 18.192.3.151/join-team/index.php?jobs to 18.192.3.151/join-team/index.php?data/filename.pdf we get a string "test" wich means we are able to execute PHP code through the pdf file sent.
        Lets create a Backdoor to be able to get a connection between the web server side and our side.
        Here i suggest using weevely to use a written php backdoor by writing  in the terminal "weevely generate pass /home/kali/Desktop/backdoor.php" to generate a backdoor file. PS:I don't recommend using backoor as a name, maybe there is policies that stops suspicious words.
        Now go back to the browser and upload backdoor.php to the browser and in burpsuite manipulate the request by changing the filename from backdoor.pdf to backdoor.php and in the content-type to "application/pdf" and forwarded it.
        You should get a "Your cv has been uploaded succesfully in backdoor.pdf"
        In the URL delete the word"jobs" and add data/backdoor.pdf in this way we activate our backdoor. Now go back to the terminal and  type"weevely  http"://18.192.3.151/join-team/index.php?data/backdoor.pdf pass"
        type ls you should get response if you got communication error re-generate another backdoor file and re-upload it to the web and re-type what you did before in the terminal, Dont forget to change the name of the file.
        type cat index.php, The flag is located on the second line of this file (Submit the flag without the ')
