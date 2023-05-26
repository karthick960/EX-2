# IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# EXP: 2

# DATE:15-03-2023

# AIM :
## To write a python program to perform stop and wait protocol


# ALGORITHM :
## 1. . Start the program.
## 2. Get the frame size from the user
## 3. To create the frame based on the user request.
## 4. To send frames to server from the client side.
## 5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
## 6. Stop the program

# CLIENT PROGRAM :
```PYTHON 3 

import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# SERVER PROGRAM :
```PYTHON 3
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())

```
# SERVER OUTPUT:

![7dd67d51-1fb5-4bb1-96a9-b53cbab34991](https://github.com/karthick960/EX-2/assets/121215938/fd71d77b-723d-4c75-a8a6-32085412055a)



# CLIENT OUTPUT :

![4240fd0e-f5ba-4982-b03d-d74a53d6886c](https://github.com/karthick960/EX-2/assets/121215938/2dff49b1-713f-4dce-9dcd-3884c93407c0)



# RESULT :
## Thus, python program to perform stop and wait protocol was successfully executed.


