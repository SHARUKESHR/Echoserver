# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
```py
SERVER.py:

import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
 
 
 CLIENT.py
 
 import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"SHARUKESH")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## CLIENT OUTPUT:

![Screenshot 2024-09-04 190245](https://github.com/user-attachments/assets/a81dc1fc-7491-4fc6-aac9-d72bd20a5065)

## SERVER OUTPUT:
![Screenshot 2024-09-04 190232](https://github.com/user-attachments/assets/926eb136-45ea-440b-8dcf-72f301a9b0c3)

## RESULT:
The program is executed successfully
