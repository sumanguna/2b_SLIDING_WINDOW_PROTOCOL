# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### NAME: Suman G
### REG.NO:212223240163
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Server
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
### Client
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### Server
<img width="936" alt="Screenshot 2024-04-09 at 10 34 17 AM" src="https://github.com/aaron-h-2k5/2b_SLIDING_WINDOW_PROTOCOL/assets/144250957/0e7e8ab7-69f6-49e5-8d82-89db3755fe13">

### Client
<img width="936" alt="Screenshot 2024-04-09 at 10 34 23 AM" src="https://github.com/aaron-h-2k5/2b_SLIDING_WINDOW_PROTOCOL/assets/144250957/bb3a9796-7101-484e-a259-b5ea603e8011">



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
