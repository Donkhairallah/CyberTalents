# CyberTalents
 Cybertalents web security challenges write-ups
 Web-Security: 
 
 Challenge name: Admin has the power

  In this challenge we have a login page that asks for username and password by inspecting the elements we can see that there a useful comment "username=support pass=.."
  Lets open BurpSuite to intercept the traffic before sending anything and connect the proxy 
  Forward the intercepted traffic from burpsuite and we get support user page.Now lets reload the page and check the request, in the coockie section there is an intersting part where role=support, change the role to admin and you get your FLAG!