# HTTP
It is a query base protocol.

# Curl
Simple request:
~~~
$ curl google.com
~~~

We can get the header response of our request with ```-I``` option:
~~~
$ curl -I google.com 
~~~ 
We will get:
~~~
HTTP/1.1 301 Moved Permanently
Location: http://www.google.com/
Content-Type: text/html; charset=UTF-8
Date: Tue, 24 Apr 2018 12:25:38 GMT
Expires: Thu, 24 May 2018 12:25:38 GMT
Cache-Control: public, max-age=2592000
Server: gws
Content-Length: 219
X-XSS-Protection: 1; mode=block
X-Frame-Options: SAMEORIGIN
~~~

If the response had a 301 Moved we can continue to that page with ```-l``` option:
~~~
$ curl -l google.com
~~~

We can write the response to a file with ```-o``` option:
~~~
$ curl -o index.html www.google.com
~~~
This will save the www.google.com response to the index.html file.


We can download and save bytes we have download and resume to download with this command :
~~~
$ curl -C - -O downloding_link_.mkv
~~~

To divide our file to many parts we can use this command: 
~~~
$ curl -r 1-10000000 -o p1 some_url_to_download.mkv
~~~
This will write from bit 1 to 10000000 to file p1.

~~~
Read header and get the size
Make 4 session and download with these sessions separated.
Merge separated files.
~~~

To run wireshark on eth:
~~~
sudo wireshark -i eth0 -k
~~~