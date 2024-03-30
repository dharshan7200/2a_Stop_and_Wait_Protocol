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
CLIENT:
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000))
s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break
```
SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())

```


## OUTPUT
![Screenshot 2024-03-30 101735](https://github.com/dharshan7200/2a_Stop_and_Wait_Protocol/assets/138850116/76bbc975-eeaf-40bc-9971-c8f5b91c91fd)

![Screenshot 2024-03-30 101816](https://github.com/dharshan7200/2a_Stop_and_Wait_Protocol/assets/138850116/96aae133-4a6a-4f4f-8862-8f8b0b33dedd)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
