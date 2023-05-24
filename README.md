# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :9.3.2023

AIM :
To write a python program to perform client server model.


ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



CLIENT PROGRAM :
```
## Developed By : S.BHUVANESHWARI
## Reg No : 212221240010
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
    ```
SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
  
 ```
 
SERVER OUTPUT :
![S](https://github.com/Bhuvaneshwari-2003/19CS406-EX-1/assets/94828604/6e0ab798-0769-4385-bc51-499f62f2338a)



CLIENT OUTPUT :
![C](https://github.com/Bhuvaneshwari-2003/19CS406-EX-1/assets/94828604/ead80e17-6a45-4c36-96cf-41688bb9df48)



RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

