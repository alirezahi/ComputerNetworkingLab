# SYN
To test that syn_sent is done, first lets run a while true code like this:

~~~
while true;do netstat -nt | grep 1.2.3.4 ; sleep 1;done;
~~~

And then after that we send a tcp request like this:
~~~
nc 1.2.3.4 12345
~~~

# Filtering
To filter and not Receive the server response(```sync/ack```) we have to filter it. The command to filter from the client side is :
~~~
sudo iptables -A INPUT -s 192.168.30.154 -j DROP
~~~
And filtering from server side is :
~~~
sudo iptables -A INPUT -s 192.168.30.154 -j DROP
~~~

And to test that filtering is ok we have to :

1.run while true on client and server

2.server in listen mode

3.client send request to server


# Iptables
iptables features:
~~~
-F Flush
-A Append
-D Delete
-L list
~~~