# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM:
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM:
##SERVER:
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
##CLIENT:
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
## OUPUT:

<img width="1904" height="1068" alt="Screenshot 2026-05-22 134053" src="https://github.com/user-attachments/assets/2407a295-64e6-476d-b018-4e4a011c355a" />


<img width="1907" height="591" alt="Screenshot 2026-05-22 134113" src="https://github.com/user-attachments/assets/1cf6d7c8-79b0-44ac-b581-555f89484db8" />


<img width="1907" height="505" alt="Screenshot 2026-05-22 134124" src="https://github.com/user-attachments/assets/3e0e89a4-e7ad-4ffc-9071-80ad0258978b" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
