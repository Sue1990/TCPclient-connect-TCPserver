# TCPclient-connect-TCPserver


TCP Client:<\br>

import socket<\br>

host='0.0.0.0'<\br>
port=50007<\br>

client=socket.socket(socket.AF.INET,socket.SOCK_STREAM)<\br>
client.connect((host,port))<\br>
print 'Ready to send "Hello server...." '<\br>
client.sendall('Hello server.... I am client')<\br>
data=client.recv(4096)<\br>
print 'Accept data from server',repr(data)<\br>






