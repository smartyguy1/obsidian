# Routers
To route data from one place to another, we need to make routing decisions. That is, someone needs to program how data is transferred from point A to point B. TCP/IP are two protocols that allow computers to transfer data between them over the internet.\

IP or *internet protocol* is a way by which computers can identify one another across the internet. Every computer has a unique address in the world. Addresses are in this form:
`#.#.#.#`

Numbers range from 0 to 255. IP addresses are 32-bit, meaning that these addresses could accommodate over 4 billion addresses. Newer versions of IP addresses, implementing 128-bits, can accommodate far more computers.

The data packets that get transferred are structured as follows:
```
0                   1                   2                   3  
0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|Version|  IHL  |Type of Service|          Total Length         |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|         Identification        |Flags|      Fragment Offset    |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|  Time to Live |    Protocol   |         Header Checksum       |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                       Source Address                          |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Destination Address                        |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Options                    |    Padding    |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

TCP: Transmission Control Protocol, helps keep track of the sequence of packets being sent. It is used distinguish web services from one another. For ex: `80` is used to denote HTTP and `443` is used to denote HTTPS. These numbers are *port numbers*.
When information is sent from one location to another, source IP address, a destination IP address and a TCP port number are sent.

These protocols are also used to fragment large files into multiple packets. When a packet is lost, TCP/IP can request missing packets again from the origin server.

TCP will acknowledge when all the data has been transmitted and received.

# DNS

It would be very tedious if you needed to remember an IP address to visit a website.
- It stands for *Domain Name System*, is a collection of servers on the internet that are used to route to website addresses.
- DNS is simply a table or database that links specific, fully qualified domain names to specific IP addresses.

# DHCP
It is a protocol that ascertains the IP address of your device
Further, this protocol defines the default gateway and nameservers your device uses.

# HTTPS
*HyperText Transfer Protocol* is an application-level protocol that developers use to build powerful and useful things through the transfer of data from one place to another. *HTTPS* is a secure version of this protocol.

- When you see an address such as `https://www.example.com` you are actually implicitly visiting that address with a `/` at the end of it.
- The _path_ is what exists after that slash. For example, `https://www.example.com/folder/file.html` visits `example.com` and browses to the `folder` directory, and then visits the file named `file.html`.
-  The `.com` is called a _top-level domain_ that is used to denote the location or type of organization associated with this address.
- `https` in this address is the protocol that is used to connect to that web address. By protocol, we mean that HTTP utilizes `GET` or `POST` _requests_ to ask for information from a server. For example, you can launch Google Chrome, right-click, and click `inspect`. When you open the `developer tools` and visit `Network`, selecting `Preserve log`, you will see `Request Headers`. You’ll see mentions of `GET`. This is possible in other browsers as well, using slightly different methods.
  
For example, when issuing a GET request, your computer may send the following to a server:

```
GET / HTTP/2
Host: www.harvard.edu
```

Generally, after making a request to a server, you will receive the following in `Response Headers`:
```
HTTP/2 200
Content-Type: text/html
```

