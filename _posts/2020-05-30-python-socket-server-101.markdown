---
layout: post
title:  "Python - Echo TCP Server "
subtitle: Exemplo de um servidor de echo 
description: Exemplo de código de um servidor de Echo escrito em python
date:   2020-05-30 12:00:00 -0300
comments: true
categories: python sockets
image: /hp/img/icon-python-001.png
hero_image: /hp/img/topo-004.jpg
tags:
  - python 
  - sockets
author: Luis Rodrigo
---

# Python:Socket - Exemplo de um servidor 

Exemplo de código em python de um servidor de echo.


```python
#!/usr/bin/env python3
"""
Aulas de PCD - Introducao ao Python 3
Prof. Luis Rodrigo

Versão:
	1.0 - 27/04/2020 - Versao original

Descrição:
	Exemplo de TCP Socket - Echo Server
"""
from termcolor import colored, cprint
import socket
import sys 

HOST = '127.0.0.1'  
PORT = 65015       


def main():
	s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

	s.connect((HOST, PORT))

	s.sendall(b'Hello, world')

	data = s.recv(1024)

	#print('Received', repr(data))
	#print('Received', str(data))
	try:
	    sys.stdout.write("Msg Recebida: %s\n" %(data.decode('utf-8')))
	except UnicodeDecodeError:
		sys.stdout.write("Msg Recebida: \n")

if __name__ == "__main__":
	main()

```
