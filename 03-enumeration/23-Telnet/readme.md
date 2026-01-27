Port 23 telnet TCP

TCP is specifically vulnerable because it does not encrypt data at all and sends passwords and user info in plaintext 


I will target this port as it may provide me with information and access In a simple process without need for complex decryption

we begin with banner grabbing, trying to interc at with the service.
telnet 192.168.1.122

after running the telnet command a banner dsiplayed, expicitly showing the login credentials for the system, an obvious vuneablity. 


since the vunerabolty was too obvious and unrealsitic i cghhose to ingnore these credntials. 
instead i aim to exploit the plain text vunerablity of telnet through packet sniffing. 




PACKET SNIFFING: METAPLOITABLE 2 Wireshark
