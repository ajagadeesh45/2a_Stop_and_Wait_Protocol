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
``` py
CLIENT:
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
``` py
SERVER:
impoimport socket
s = socket.socket()
s.connect(('localhost', 8000))
whilwhile True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
  CLIENT
![Screenshot 2025-03-18 114634](https://github.com/user-attachments/assets/4455365f-23c8-4489-a596-433573d96c96)
 SERVER
![Screenshot 2025-03-18 114652](https://github.com/user-attachments/assets/ab5cd615-569b-4cfa-863b-414eda04a868)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
