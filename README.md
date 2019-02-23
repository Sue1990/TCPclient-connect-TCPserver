# TCPclient-connect-TCPserver


TCP Client:

import socket<br>

host='0.0.0.0'<br>
port=50007

client=socket.socket(socket.AF.INET,socket.SOCK_STREAM)#AF_INET：使用標準的IPv4地址或主機名，SOCK_STREAM：說明這是一個TCP服務器
client.connect((host,port))
print 'Ready to send "Hello server...." '
client.sendall('Hello server.... I am client')
data=client.recv(4096)
print 'Accept data from server',repr(data) ＃印出伺服器傳回來的資料




TCP Server:

import socket

ip=' '
port=50007

server=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
server.bind((ip,port))
server.listen(5)
conn,addr=server.accept()
print 'connect address',repr(addr)      
#also can use str instead of repr , different way is : 
#(1)use 'repr' ,when you printed , it will show ''
#(2)use 'str'  ,when you printed , it won't show ''

#conn means : request object 
#addr means : client's address:  host:port
while True:
  data=conn.recv(4096)
  if not data: break
  print repr(data)
  conn,sendall(data) # 把從客户端接收来的資料，完整發送给客户端
conn.close()
  





