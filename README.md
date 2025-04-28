# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM:
To write a python program for creating File Transfer using TCP Sockets Links

## ALGORITHM:
Import the necessary python modules.
Create a socket connection using socket module.
Send the message to write into the file to the client file.
Open the file and then send it to the client in byte format.
In the client side receive the file from server and then write the content into it.
## PROGRAM:

Name: SHYAM S  
Register No: 212223240156

### Client:
```
import socket

client = socket.socket()
host = socket.gethostname()
port = 60000
client.connect((host, port))

with open('received_file.txt', 'wb') as f:
    while True:
        data = client.recv(1024)
        if not data:
            break
        f.write(data)

print('File received successfully.')
client.close()

```
### Server:
```
import socket

server = socket.socket()
host = socket.gethostname()
port = 60000
server.bind((host, port))
server.listen(1)

print('Waiting for connection...')
conn, addr = server.accept()
print('Connected to', addr)

with open('mytext.txt', 'rb') as f:
    data = f.read(1024)
    while data:
        conn.send(data)
        data = f.read(1024)

print('File sent successfully.')
conn.close()
server.close()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/ccca8231-2299-46b7-87df-9d619422fe7e)

![image](https://github.com/user-attachments/assets/8dbe902b-0488-4e79-9e24-21962c1e52c6)

## RESULT:
Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.

