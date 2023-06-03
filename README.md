# STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODAL

# EXP: 1

# DATE :06-03-2023

# AIM :
## To implement socket programming date and time display from client to server using TCPSockets

# ALGORITHM :
## SERVER PROGRAM:
## 1. Create a server socket and bind it to port.
## 2. Listen for new connection and when a connection arrives, accept it.
## 3. Send server‟s date and time to the client.
## 4. Read client‟s IP address sent by the client.
## 5. Display the client details.
## 6. Repeat steps 2-5 until the server is terminated.
## 7. Close all streams.
## 8. Close the server socket.
## 9. Stop.


# CLIENT PROGRAM :
## 1. Create a client socket and connect it to the server‟s port number.
## 2. Retrieve its own IP address using built-in function.
## 3. Send its address to the server.
## 4. Display the date & time sent by the server.
## 5. Close the input and output streams.
## 6. Close the client socket.
## 7. Stop.

# CLIENT PROGRAM :
```PYTHON 3
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
# SERVER PROGRAM : 
```PYTHON 3
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
```

# CLIENT OUTPUT : 
![IMG-20230527-WA0020](https://github.com/ARUNKUMART9968/19CS406-EX-1/assets/121215794/776252bb-9f63-4361-b551-55aa746effd5)
# SERVER OUTPUT :
![IMG-20230527-WA0021](https://github.com/ARUNKUMART9968/19CS406-EX-1/assets/121215794/6ff91ac9-c4d2-44f3-9ce9-c2195c6dab42)



# RESULT:
## Thus, the program to implement socket programming date and time display from client to server
using TCP Sockets was successfully executed ##
