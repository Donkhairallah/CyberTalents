# CyberTalents
 Cybertalents web security challenges write-ups
 Web-Security: 
 
 Challenge name: Iam Legend

 In this challenge we have a login page 
 By inspecting the elements we can notice a script. While looking at the script we can see that this script is formed by special characters. After searching for this type of encryption i found a programing language called JSFuck which is formed of only 6 characters. Not all JSFUCK can decode this script there is only few websites that can decode this specific script.By converting this script to plain text
 we get multiple functions, but there is one function that we are intersted in which is the check function , in this fucntion we see an if statement (user==Cyber and pass == Talent).
 By entering these credentials we get a pop-up that has the flag in it  