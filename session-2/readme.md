# Network Definition
## Path
Longest path can be determined by the number of hubs that the path has.(It is a dynamic routing)

## Errors
It is not necessary for a device to respond all errors.It can be set that if the device is busy it will not send the errors and will ignore them, if it is free it will send the errors.

## Port
Every application in a device need to have a port to be known to others.

## Ping
When we ping the application that we are going through is ping and the response is coming from the OS application.

## Netsat
The ```-l``` will return the listening ones.
The ```-p``` will return the process.

```netstat -ntl``` will return TCP connections.

```netstat -nul``` will return UDP connections.

```netstat -nt``` will return nt connections.

## 127.0.0.1
```127.0.0.1``` is Ourselves.

## Server-Client application

TCP :
Server Mode : 
~~~consoleszzc fdsffdsssdfcx 
#!/bin/bash
$ nc -l -p 12345
~~~

Client Mode : 
~~~
nc 127.0.0.1 12345
~~~

UDP :
Server Mode : 
~~~consoleszzc fdsffdsssdfcx 
#!/bin/bash
$ nc -l -u -p 12345
~~~

Client Mode : 
~~~
nc -u 127.0.0.1 12345
~~~

### Difference
The difference between ```UDP``` and ```TCP``` is that if the server is not establish in the ```TCP``` then your client won't connect and won't response. But in ```UDP``` if the server is not connected the client will connect but just won't response.

So if the server is not established in UDP:
* client can connect
* client won't respond

So if the server is not established in TCP:
* client can't connect
* client won't respond