# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### NAME: Suman G
### REG.NO:212223240163
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
![320813765-68e67df6-3f82-449c-8159-c2f81e6b304f](https://github.com/22002525karthikeyan/2b_SLIDING_WINDOW_PROTOCOL/assets/118708040/7bcba08d-715d-417c-b8ab-fe584727e089)
### Client
![320813914-82d9e11a-fb40-49c9-a9ea-44f7aa5d9ed0](https://github.com/22002525karthikeyan/2b_SLIDING_WINDOW_PROTOCOL/assets/118708040/d81a1f40-2d87-49c6-b196-e4cdf9c4a792)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
