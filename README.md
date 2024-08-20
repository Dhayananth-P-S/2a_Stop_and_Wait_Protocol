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
import socket
s=socket.socket()
s.bind(('localhost',8080))
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


import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
## OUTPUT
PS C:\maphtml> & C:/Users/admin/AppData/Local/Microsoft/WindowsApps/python3.11.exe c:/maphtml/importsocket.py
Enter a data: 50
Acknowledgement Recived
Enter a data: hey
Acknowledgement Recived
Enter a data: rest in peace
Acknowledgement Recived
Enter a data: 


PS C:\maphtml> & C:/Users/admin/AppData/Local/Microsoft/WindowsApps/python3.11.exe c:/maphtml/serversocket.py
50
hey
rest in peace

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
