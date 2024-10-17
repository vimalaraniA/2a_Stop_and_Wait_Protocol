# 2a_Stop_and_Wait_Protocol

## Developed by: Vimala Rani A
## Register no: 212223040240

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
## Client:
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

```
## OUTPUT
## Client:

![Screenshot 2024-05-07 091940](https://github.com/PreethiS647/2a_Stop_and_Wait_Protocol/assets/147313372/4a828ce2-4ad0-4c10-be96-227e3334d97d)

## Server:

![Screenshot 2024-05-07 092003](https://github.com/PreethiS647/2a_Stop_and_Wait_Protocol/assets/147313372/fa7d4acd-c61d-4a37-8a31-7ab5c0038eda)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
