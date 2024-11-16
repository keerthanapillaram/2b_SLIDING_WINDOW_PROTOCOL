# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name : Keerthana P 
## Register number : 212223240069
## AIM
To write a program to implement sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Name    : P Keerthana
Reg NO. : 212223240069
```

## Client :
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size: "))
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("acknowledgement received from the server".encode())
```
## Output :
## Client :
![Screenshot 2024-09-25 091105](https://github.com/user-attachments/assets/c51ed661-7cc4-4fd6-969f-1862c11a0210)



## Server:
![Screenshot 2024-09-25 091114](https://github.com/user-attachments/assets/27160673-9b28-45b1-9bf7-b50949591938)

## Result:
Thus the study on Client Server Chat Applications has been performed
