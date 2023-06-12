### EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL:
```
DATE : 23-03-2023
```
### AIM :
To write a python program to perform sliding window protocol.

### ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will 
  send NACKsignal to client.
6.Stop the program.
```
### PROGRAM :
```
Developed by: M Gautham
Reg. No: 212221230027
```
## Client Side:
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
## Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
### OUTPUT :
## Client Side:

![image](https://github.com/muppirgautham/EX-3/assets/94810884/95817d65-80e9-470a-8282-60501f42a527)
## Server Side:
![image](https://github.com/muppirgautham/EX-3/assets/94810884/98c8e92e-677f-4d77-8a09-79e5db15895f)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.


