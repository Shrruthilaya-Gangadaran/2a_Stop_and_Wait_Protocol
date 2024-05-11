<H1 ALIGN=CENTER> STOP AND WAIT PROTOCOL </H1>
<H3> NAME : SHRRUTHILAYA G </H3>
<H3> REGISTER NUMBER : 212221230097 </H3>
<H3>EXPERIMENT NO : 02 A </H3>
<H3>DATE  : 11.05.2024 </H3>

## AIM:
To write a python program to perform stop and wait protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client.
6. Stop the Program.

## PROGRAM:
### CLIENT:
```
import socket
s = socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data : ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
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
s = socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgment Received".encode())
```

## OUTPUT:

### CLIENT:
![Client](https://github.com/Shrruthilaya-Gangadaran/2a_Stop_and_Wait_Protocol/assets/93427705/7ced9352-ac66-4a56-90e9-84f3169c6a33)


### SERVER:

![Server](https://github.com/Shrruthilaya-Gangadaran/2a_Stop_and_Wait_Protocol/assets/93427705/e0184249-3f8d-4ed7-966a-3d0a33126465)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
