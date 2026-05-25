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
<img width="1689" height="784" alt="image" src="https://github.com/user-attachments/assets/5f4ca44f-b7c6-4190-9504-1845137dad32" />
## SERVER.PY:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/c78ac126-16eb-4a25-9338-844a289ae077" />
## CLIENT.PY:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/a036bbbc-7994-49f2-a402-4c65a7aa2711" />
## RECEIVED.TXT:
<img width="1906" height="286" alt="image" src="https://github.com/user-attachments/assets/8740d888-b7ff-47c9-964b-07e89cb481c0" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
