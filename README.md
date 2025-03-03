# EXP-01-Echoserver
Echo server and client using python socket
# REGISTER NUMBER: 212223100025
# DATE :

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
SERVER SIDE:
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    try:
        s.bind((HOST, PORT))
    except Exception as e:
        print(f"Error binding to {HOST}:{PORT}: {e}")
        exit()
    
    s.listen()
    print(f"Listening on {HOST}:{PORT}...")

    try:
        conn, addr = s.accept()
    except Exception as e:
        print(f"Error accepting connection: {e}")
        exit()

    with conn:
        print(f"Connected by {addr}")
        while True:
            try:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
            except Exception as e:
                print(f"Error receiving/sending data: {e}")
                exit()



```
CLIENT CODE:
```
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Lekasri 03-03-2025")
    data = s.recv(1024)

print(f"Received {data!r}")

```
## OUTPUT:
SERVER:
![Screenshot 2025-03-03 114804](https://github.com/user-attachments/assets/690ae136-3851-4dcb-9f85-a5556c0d1249)

CLIENT:
![Screenshot 2025-03-03 114824](https://github.com/user-attachments/assets/3bf45636-ebf2-4736-aa7a-fab7f50fe3dc)



## RESULT:
The program is executed successfully
