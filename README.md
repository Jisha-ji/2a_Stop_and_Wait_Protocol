# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## SERVER

```
import socket 

s = socket.socket() 
s.bind(('localhost', 9000)) 
s.listen(5) 

c, addr = s.accept()

while True:
    i = input("Enter a data: ") 
    c.send(i.encode()) 

    ack = c.recv(1024).decode() 
    if ack:
        print(ack) 
        continue
    else:
        c.close() 
        break
```
## CLIENT

```
import socket 

s = socket.socket() 
s.connect(('localhost', 9000)) 

while True: 
    data = s.recv(1024).decode()
    if not data:
        break
    print(data)
    s.send("Acknowledgement Received".encode())
```
## OUTPUT

## SERVER

<img width="649" height="1077" alt="Screenshot 2025-09-19 105753" src="https://github.com/user-attachments/assets/1a3aaa2a-9993-493d-a892-da479f4d687e" />

## CLIENT

<img width="636" height="1029" alt="Screenshot 2025-09-19 105833" src="https://github.com/user-attachments/assets/f4e32598-14ba-454c-acba-8f0e542d2672" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
