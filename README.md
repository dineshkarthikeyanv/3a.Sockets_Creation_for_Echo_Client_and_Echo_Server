# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
## REG NO :212225230060
## Date : 17/11/2026
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
Server:
```
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))

server_socket.listen(1)
print("Echo Server is waiting for connection...")

client_socket, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    data = client_socket.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    client_socket.send(data.encode())

client_socket.close()
server_socket.close()
```
Client:
```
import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = '127.0.0.1'
port = 5000
client_socket.connect((host, port))

while True:
    message = input("Enter message: ")

    client_socket.send(message.encode())

    if message.lower() == 'exit':
        break

    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)

client_socket.close()
```
## OUPUT
Server:
<img width="1917" height="1025" alt="image" src="https://github.com/user-attachments/assets/891e4044-6ea1-476b-baac-d665643dff8e" />
Client:
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/fda8dad9-ecde-4f78-a2f7-e923d5c788ba" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
