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
Server code


# echo-server.py

```
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

Client Code:
# echo-client.py


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")
```

## OUTPUT:

### SERVER:

![Screenshot from 2023-08-31 15-52-54](https://github.com/Dhanashreemullaithasan/Echoserver/assets/94165415/c7c8893b-4d09-4cf9-bb5c-9e234c9cebc8)
### CLIENT:

![Screenshot from 2023-08-31 15-53-09](https://github.com/Dhanashreemullaithasan/Echoserver/assets/94165415/03f43172-21ad-4caf-ba38-8de0730c2881)


## RESULT:
The program is executed successfully
