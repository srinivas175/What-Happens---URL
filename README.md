# What-Happens---URL
A Summary on what happens when a URL is typed in browser
## Description
The URL requests and the process of how browser accepts the URL and handles it, how information is rendered from the specified url's server are briefed as steps in this article.
## Step-1
**When we enter text in the address bar of browser**

While entering the text in the URl bar or search bar of the browser, it receives the event and starts auto-complete function.Depending on browser's algorithm various suggestions will be presented in the dropbox below the URL bar. Most of these algorithms sort and prioritize results based on search history, bookmarks, cookies, and popular searches from the internet as a whole. It may even suggest "google.com" before you finish typing it.
## Step-2
**Parsing the URL**

The browser adds the **_https:_** or **_http_** to the URL as a protocol as a part of parsing
## Step-3 
**URL or Search Item???**

Now, the browser aslo does the job of differentiating whether the entered is text is a URl or a search item. When no protocol or valid domain name is given the browser proceeds to feed the text given in the address box to the browser's default web search engine.
## Step-4
**DNS Lookup**

The Domain Name System maintains the name of the website (URL) and the particular IP address it links to. Every single URL on the internet has a unique IP address assigned to it.
- Browser checks if the domain is in its 4 caches : **Browser Cache, OS cache, Router Cache,  ISP cache**
- If not found, DNS calls the ISP’s DNS server, a DNS recursor that finds the proper IP address of the intended domain name by querying with other DNS servers(called name servers) on the internet for an answer.
- If the DNS server is on the same subnet the network library follows the **ARP(Address Resolution Protocol) process** below for the DNS server.
- If the DNS server is on a different subnet, the network library follows the ARP process below for the default gateway IP.
## Step-5
**Opening Socket**
- Once the DNS fetches the IP Address of the required server, it takes that and the given port number from the URL ( For **HTTP protocol** - **Port 80**, and **HTTPS** - **Port 443**), and makes a call to the system library function named socket and requests a **TCP socket stream**
## Step-6
**TCP Connection Handshake**
1. The server creates the listener socket that is waiting for remote clients to connect.
2. The client issues the connect() socket function to start the TCP handshake (SYN, SYN/ACK, ACK). 
3. The server issues the accept() socket function to accept the connection request.
4. The client and server issue the read() and write() socket functions to exchange data over the socket.
## Step-7
**HTTP Protocol**

After a successful TCP handshake is established,the browser send the GET request asking for the web page.

## Step-8
**HTTP Server Request Handle**

The destination ins a web server, which receives the request from the browser and passes it to a request handler to read and generate a response. Then it will assemble a response in a particular format.
The server breaks down the request to the following parameters:
1. HTTP Request Method (either GET, HEAD, POST, PUT, DELETE, CONNECT, OPTIONS, or TRACE). In the case of a URL entered directly into the address bar, this will be GET.
2. Domain
3. Requested path/page, in this case - / (as no specific path/page was requested, / is the default path).

## Step-9
**HTTP Server Response**

The server response contains the web page you requested as well as the status code, compression type (Content-Encoding), how to cache the page (Cache-Control), any cookies to set, privacy information, etc.
