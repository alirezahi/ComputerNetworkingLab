# Computer Networking

Every device that has an IP, also has a ```Routing Table``` which shows all the routes.

## netstat
We can get IPs and routing table with command ```netstat -r```.

## Routing Table
For example let's have this routing table:
~~~
Destination     Gateway
default(0.0.0.0)     172.23.160.1
192.168.1.15        192.168.1.1
192.168.1.0     192.168.1.2
~~~
If we want to go to ```192.168.1.15``` we go from that ip and its gateway, and if we want to go to ```192.168.1.x``` that x is not 15 we will go from 192.168.1.2 gateway and for others we go by gateway of 172.23.160.1.

## DNS
The one which knows all the IPs.

## Network Card
Network cards are set to ```DHCP```.Our home DHCP server is modem.

When we send DHCP we will get IP, DNS etc.

## Traceroute
It will display route to our destination.

command in mac and linux kernel is ```traceroute``` and in windows is ```tracert```

Example:
~~~console
$ traceroute 8.8.8.8
traceroute to 8.8.8.8 (8.8.8.8), 64 hops max, 52 byte packets
 1  172.23.160.1 (172.23.160.1)  1.824 ms  1.545 ms  1.246 ms
 2  172.16.4.4 (172.16.4.4)  1.223 ms  4.243 ms  1.249 ms
 3  172.29.1.3 (172.29.1.3)  1.583 ms  1.641 ms  0.881 ms
 4  * * *
 5  194.225.32.1 (194.225.32.1)  3.203 ms  3.599 ms  1.947 ms
 6  nia-sw-150-20.ipm.edge-2.iranet.ir (194.225.150.20)  2.288 ms  2.299 ms  2.716 ms
 7  l-6-vl06.lct-ro-151-45.ipm.edge-1.iranet.ir (194.225.151.45)  3.848 ms  4.149 ms  3.834 ms
 8  85.132.60.73 (85.132.60.73)  14.874 ms  14.910 ms  57.282 ms
 9  * * *
10  72.14.203.212 (72.14.203.212)  1097.158 ms  725.164 ms
    72.14.195.224 (72.14.195.224)  50.258 ms
11  108.170.250.177 (108.170.250.177)  54.403 ms  53.894 ms  55.162 ms
12  216.239.63.61 (216.239.63.61)  49.812 ms
    216.239.41.103 (216.239.41.103)  55.449 ms
    216.239.63.57 (216.239.63.57)  48.789 ms
13  google-public-dns-a.google.com (8.8.8.8)  45.701 ms  45.785 ms  45.272 ms
~~~

## TTL
TTL is defined to set a counter to see if the request passes the limit, send an error to the source.

## Ping
If you want to ping n times you need to ping with ```ping 8.8.8.8 -c n```

for example for 5 times : ```ping 8.8.8.8 -c 5```

```ping -m 1```.In this command ```-m 1``` sets the TTl to 1.

## Two network card
If you're connected to internet via WIFI and WLAN you can see which is going you from with the default in ```netstat -r```.

## FT
FTTH : Fiber to the home

FTTX : Fiber to anything!

## Built in Traceroute
Bash script for tracerouting:
~~~
for i in {1..10}; ping 8.8.8.8 -c 1 -m$i | grep exceeded;done
~~~

For debuggig we can write echo:
~~~
for i in {1..10}; do echo $i;ping 8.8.8.8 -c 1 -m$i | grep exceeded;done
~~~

## Netcat
You can establish client server app with netcat that its application in mac is called ```nc```
```nc -ul 8000```
```nc -u 127.0.0.1 8000```