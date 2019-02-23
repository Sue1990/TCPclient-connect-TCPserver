# TCPclient-connect-TCPserver


TCP Client:<br>

import socket<br>

host='0.0.0.0'<br>
port=50007<br>

client=socket.socket(socket.AF.INET,socket.SOCK_STREAM)#AF_INET：使用標準的IPv4地址或主機名，SOCK_STREAM：說明這是一個TCP服務器<br>
client.connect((host,port))<br>
print 'Ready to send "Hello server...." '<br>
client.sendall('Hello server.... I am client')<br>
data=client.recv(4096)<br>
print 'Accept data from server',repr(data) ＃印出伺服器傳回來的資料<br>




TCP Server:<br>

import socket<br>

ip=' '<br>
port=50007<br>

server=socket.socket(socket.AF_INET,socket.SOCK_STREAM)<br>
server.bind((ip,port))<br>
server.listen(5)<br>
conn,addr=server.accept()<br>
print 'connect address',repr(addr)<br>
#also can use str instead of repr , different way is : <br>
#(1)use 'repr' ,when you printed , it will show ''<br>
#(2)use 'str'  ,when you printed , it won't show ''<br>

#conn means : request object <br>
#addr means : client's address:  host:port<br>
while True:<br>
  data=conn.recv(4096)<br>
  if not data: break<br>
  print repr(data)<br>
  conn,sendall(data) # 把從客户端接收来的資料，完整發送给客户端<br>
conn.close()<br>
  





