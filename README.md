# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

## DATE : 13-03-2023

## AIM:
To write a python program to perform stop and wait protocol

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program


## PROGRAM:
### CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break
 ```
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 ```
## OUTPUT:  

### CLIENT:
![240957673-0e37799e-a40a-4c4f-b83e-32658daa7edd](https://github.com/Mena-Rossini/EX-2/assets/102855266/02059f4a-8747-4f46-8dbc-e8289ccb2165)

### SERVER:

![240957710-952c947e-3d4c-46ef-acc9-f555432153c9](https://github.com/Mena-Rossini/EX-2/assets/102855266/992f8ceb-9331-4233-b3f7-cd2a4e3aaad1)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

