# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.

## PROGRAM:
### CLIENT:
```python
#NAME: RAKSHITHA J
#REG NO: 212223240135


import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000)) 
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr) 
now = datetime.now() 
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode() 
if ack:
    print(ack)
c.close()
```
### SERVER:
```python
#NAME:RAKSHITHA J
#REG NO: 212223240135

import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
print(s.getsockname()) 
print(s.recv(1024).decode()) 
s.send("acknowledgement recived from the server".encode()) 
```
## OUTPUT :
### CLIENT AND SERVER :

![2c client nd server](https://github.com/user-attachments/assets/3d0819ab-de6f-4b34-b2a6-c3f6f3b89c4e)

## RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
