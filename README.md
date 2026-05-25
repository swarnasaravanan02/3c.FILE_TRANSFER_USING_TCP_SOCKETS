## NAME: SWARNA PRIYA S
## REG.NO: 212225040447
# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## SAMPLE.TXT:
Hello Python Socket Programming
## SERVER.PY:
```
import socket
# Create socket
server = socket.socket()
# Bind IP and port
server.bind(("127.0.0.1", 5555))
# Listen for client
server.listen(1)
print("Server waiting for connection...")
# Accept client
client, addr = server.accept()
print("Connected to:", addr)
# Ask filename
filename = input("Enter file name to send: ")
# Open and send file
with open(filename, "rb") as file:
 data = file.read()
 client.send(data)
print("File sent successfully")
# Close connections
client.close()
server.close()
```
## CLIENT.PY:
```
import socket
# Create socket
client = socket.socket()
# Connect to server
client.connect(("127.0.0.1", 5555))
# Save file name
save_name = input("Enter name to save file: ")
# Receive data
data = client.recv(1000000)
# Save file
with open(save_name, "wb") as file:
 file.write(data)
print("File received successfully")
# Close connection
client.close()
```
## OUPUT
## SAMPLE.TXT:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/40426a65-b6f6-4473-8d4b-fbef7a73d6f9" />

## SERVER.PY:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/f71ef3ef-ca84-473d-86c8-e7f876e19f51" />

## CLIENT.PY:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/5d694b3b-591b-4d08-bc65-ae9372d2cb8f" />

## RECEIVED.TXT:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/43a2323f-37ab-4bdd-9613-5ce4b2efe68e" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
