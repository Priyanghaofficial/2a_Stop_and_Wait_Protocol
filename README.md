# 2a_Stop_and_Wait_Protocol
# REGISTER NO:212223040157
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
client:
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
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
```
## OUTPUT
client output:

![image](https://github.com/Priyanghaofficial/2a_Stop_and_Wait_Protocol/assets/147121154/0b018be0-4186-43df-963b-b44b7819aa2c)

server output:

![image](https://github.com/Priyanghaofficial/2a_Stop_and_Wait_Protocol/assets/147121154/822001c9-16ea-4c30-ad31-817710819bcf)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
