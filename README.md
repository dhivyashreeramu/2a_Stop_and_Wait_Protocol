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
client side :
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
server side:
```  
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

client :
<img width="1061" height="506" alt="image" src="https://github.com/user-attachments/assets/b7edc824-5e2c-4719-aee2-b0371bfc6315" />

server:
<img width="1125" height="478" alt="image" src="https://github.com/user-attachments/assets/d5025603-37b8-4b36-bab1-0435cc9f2200" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
