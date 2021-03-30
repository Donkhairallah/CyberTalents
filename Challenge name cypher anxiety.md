# CyberTalents

Cybertalents web security challenges write-ups
Web-Security:

Challenge name: Cypher anxiety

In the challenge desscription we know that there is a image was leaked which means we are looking for an image that was leaked.Moreover in the description we kniow that the flag is the md5 of the image. We have a ZIP file,download and Unizip the file we get a pcap file, we Open it using wireshark to be able to see the network traffic and analyze it.By going threw the traffic we can see that there is a conversation going on that start in alert number 10 Source IP: 192.168.1.6 and destination IP: 192.168.1.100.Going threw this conversation we get IMPORTANT messages that these 2 users will change there conversation to an encrypted channel using cryptcat and the passowrd is P@ssawordaya using the traffic 7070.
Let's filter these network traffic by typing tcp.port == 7070. From there we need to save all network traffic that passes threw port 7070, Right-click and click on follow --> tcp stream and save it in the same folder to keep folders arranged. Here we will use Netcat as a management tool to listen on the traffic that passed on this port and decrypt it.Open terminal in the folder where we saved the file.First create a listener to netcat using netcat localhost 7070 < encrypted.This command let us intiate a listenner on port 7070 and take input from filename encrypted which is the wireshark file we saved before and we press enter we can see an error which is connection refused because we didn't set up netcat on the other endpoint. Open another terminal in the same location and now type
cryptcat -l -k P@ssawordaya -p 7070 > decrypted.
In this command we start with cryptcat which is the method of encryption followed by -l to print the output in the same folder followed by -k and the passowrd then -p for port number and put the ouptut in file named decrypted in the location that is managed by l option. You get an image named decrypted. As the challenge description mentioned that the flag is in md5 format, we use md5sum filename here it is decrypted and we get the FLAG!
