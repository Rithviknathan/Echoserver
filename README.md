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
## CLIENT
``
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")
``
## SERVER
``
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

``

## OUTPUT:
## CLIENT
![ETHICAL EXERCISE 1(2)](https://github.com/user-attachments/assets/6d8b53a8-943b-494a-8f78-64903ee2e37c)
![ETHICAL EXERCISE 1(3)](https://github.com/user-attachments/assets/48e00270-1af9-4b5f-9b8e-934e6e0d38c9)

## SERVER
![ETHICAL EXERCISE 1(1)](https://github.com/user-attachments/assets/f056613a-464a-451d-a748-b7cde86bd8c4)
![ETHICAL EXERCISE 1(4)](https://github.com/user-attachments/assets/c618cd00-0228-4256-88d2-83b8821e6920)


## RESULT:
The program is executed successfully
