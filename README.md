# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## CLIENT:
```
import socket

s = socket.socket()
s.connect(('127.0.0.1', 8000))   # use 127.0.0.1 instead of 'localhost' to avoid DNS issues
print("Client socket:", s.getsockname())

data = s.recv(1024).decode()
print("From server:", data)

s.send("Acknowledgement received from client".encode())

s.close()

```

## SERVER:
```
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
## OUTPUT

## CLIENT:
<img width="562" height="188" alt="image" src="https://github.com/user-attachments/assets/353cd37a-81b0-4deb-90ce-f2c8bc24be44" />

## SERVER
<img width="573" height="193" alt="image" src="https://github.com/user-attachments/assets/b88075f6-236a-41c6-a7b3-84d6457a2ffe" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
