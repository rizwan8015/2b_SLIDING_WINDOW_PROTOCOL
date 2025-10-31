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
## OUPUT
## RESULT
Thus, python program to perform stop and wait protocol was suc# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### CLIENT:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

size = int(input("Enter number of frames to send: "))
l = list(range(size))
w = int(input("Enter Window Size: "))

st = 0
i = 0

while True:
    while i < len(l):
        st += w
        c.send(str(l[i:st]).encode())
        ack = c.recv(1024).decode()
        if ack:
            print(ack)
            i += w

```
### SERVER:
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement received from the client".encode())

```
## OUPUT

### CLIENT:
<img width="864" height="131" alt="image" src="https://github.com/user-attachments/assets/ed560d6a-c6a5-425b-b25a-21b3006fd1ec" />


### SERVER:
<img width="910" height="101" alt="image" src="https://github.com/user-attachments/assets/2b380826-40fe-4ab6-a3c2-b1d92371c092" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
cessfully executed
