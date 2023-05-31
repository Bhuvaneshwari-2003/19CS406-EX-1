# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

# DATE :9.3.2023

# AIM :
To write a python program to perform client server model.


# ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



# PROGRAM :
# CLIENT:
Developed by : S.BHUVANESHWARI
Register Number : 212221240010
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
 c.close()
 
 # SERVER:
 Developed by : S.BHUVANESHWARI
 Register Number : 212221240010
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())

 
# OUTPUT :
# CLIENT :
![241972511-587fec7f-d45e-4f14-b2bd-37e61ddd1bbf](https://github.com/Bhuvaneshwari-2003/19CS406-EX-1/assets/94828604/e966cf6f-7175-470e-ad12-960dfb95f6b2)


# SERVER :
![241972703-b5a323c0-0b9c-4a89-89f5-6a013b7847c6](https://github.com/Bhuvaneshwari-2003/19CS406-EX-1/assets/94828604/7b569cdc-0597-4bfe-9605-7842c8bf5dbb)




# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

