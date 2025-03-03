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
![Screenshot 2025-03-03 115852](https://github.com/user-attachments/assets/a0d3736d-4656-4abe-a215-d87067ed0e0c)


CLIENT:
![Screenshot 2025-03-03 115830](https://github.com/user-attachments/assets/de6e115c-da97-4f0c-87e2-2b98d20c0b58)




## RESULT:
The program is executed successfully
