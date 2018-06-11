# Network

## Internet protocol suite - TCP/IP

### Definition	
The Internet protocol suite provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received. This functionality is organized into four abstraction layers which classify all related protocols according to the scope of networking involved. From lowest to highest, the layers are the link layer, containing communication methods for data that remains within a single network segment (link); the internet layer, providing internetworking between independent networks; the transport layer handling host-to-host communication; and the application layer, which provides process-to-process data exchange for applications.			
			
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/IP_stack_connections.svg/490px-IP_stack_connections.svg.png" class="svg">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/UDP_encapsulation.svg/800px-UDP_encapsulation.svg.png" class="svg">


### Application Layer
 The application layer is the scope within which applications create user data and communicate this data to other applications on another or the same host. The applications, or processes, make use of the services provided by the underlying, lower layers, especially the Transport Layer which provides reliable or unreliable pipes to other processes. The communications partners are characterized by the application architecture, such as the client-server model and peer-to-peer networking. This is the layer in which all higher level protocols, such as SMTP,FTP, SSH, HTTP, operate. Processes are addressed via ports which essentially represent services.

### Transport layer 
The transport layer performs host-to-host communications on either the same or different hosts and on either the local network or remote networks separated by routers. It provides a channel for the communication needs of applications. UDP is the basic transport layer protocol, providing an unreliable datagram service. The Transmission Control Protocol provides flow-control, connection establishment, and reliable transmission of data.

### Internet layer 
The internet layer exchanges datagrams across network boundaries. It provides a uniform networking interface that hides the actual topology (layout) of the underlying network connections. It is therefore also referred to as the layer that establishes internetworking, indeed, it defines and establishes the Internet. This layer defines the addressing and routing structures used for the TCP/IP protocol suite. The primary protocol in this scope is the Internet Protocol, which defines IP addresses. Its function in routing is to transport datagrams to the next IP router that has the connectivity to a network closer to the final data destination.
				
### Link layer 
The link layer defines the networking methods within the scope of the local network link on which hosts communicate without intervening routers. This layer includes the protocols used to describe the local network topology and the interfaces needed to effect transmission of Internet layer datagrams to next-neighbor hosts.

## Ethernet
TODO

## TCP
TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating by an IP network.

				<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Tcp_state_diagram_fixed_new.svg/1194px-Tcp_state_diagram_fixed_new.svg.png"
				 width="796" height="600" srcset="//upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Tcp_state_diagram_fixed_new.svg/1194px-Tcp_state_diagram_fixed_new.svg.png 1.5x, //upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Tcp_state_diagram_fixed_new.svg/1592px-Tcp_state_diagram_fixed_new.svg.png 2x"
				 data-file-width="1084" data-file-height="817">

`CLOSED --> LISTEN -- sync/sync ack --> SYNC RECEIVED -- ack/- --> ESTABLISHED
ESTABLISHED -- close/fin --> FIN WAIT 1 --fin/ack--> CLOSING -ack/--> CLOSED`
					
### Package format
TODO

## IP
TODO: How to start a session, Package format, Symetric vs asymetric conexion

## HTTP					
HTTP is an application protocol for transfer hypertext designed within the framework of the Internet protocol suite. Its definition presumes an underlying and reliable transport layer protocol,[4] and Transmission Control Protocol (TCP) is commonly used. It functions as a request–response protocol in the client–server computing model. By definition it is a stateless transaction.

### Cookies
Cookies are arbitrary pieces of data, usually chosen and first sent by the web server, and stored on the client computer by the web browser. The browser then sends them back to the server with every request, introducing states (memory of previous events) into otherwise stateless HTTP transactions. Without cookies, each retrieval of a web page or component of a web page would be an isolated event, largely unrelated to all other page views made by the user on the website. Although cookies are usually set by the web server, they can also be set by the client using a scripting language such as JavaScript (unless the cookie's HttpOnly flag is set, in which case the cookie cannot be modified by scripting languages).

### Some common request methods</h4>
- GET: The GET method requests a representation of the specified resource.
- HEAD: The HEAD method asks for a response identical to that of a GET request, but without the response body. This is
						useful for retrieving meta-information written in response headers, without having to transport the entire content.
- DELETE: The DELETE method deletes the specified resource.
- POST: The POST method requests that the server accept the entity enclosed in the request as a new subordinate of the web resource identified by the URI. The data POSTed might be, for example, an annotation for existing resources; a message for a bulletin board, newsgroup, mailing list, or comment thread; a block of data that is the result of submitting a web form to a data-handling process; or an item to add to a database.
- PUT:The PUT method requests that the enclosed entity be stored under the supplied URI. If the URI refers to an already existing resource, it is modified; if the URI does not point to an existing resource, then the server can create the resource with that URI.

### Message format
- Request
A request line (e.g., GET /images/logo.png HTTP/1.1, which requests a resource called /images/logo.png from the server).
Request header fields (e.g., Accept-Language: en).
An empty line.
An optional message body.

- Response
A status line which includes the status code and reason message (e.g., HTTP/1.1 200 OK, which indicates that the client's request succeeded).
Response header fields (e.g., Content-Type: text/html).
An empty line.
An optional message body.

### Example 
`Client request
GET /index.html HTTP/1.1 Host: www.example.com`

`Server response
HTTP/1.1 200 OK 
Date: Mon, 23 May 2005 22:38:34 GMT 
Content-Type: text/html; charset=UTF-8 
Content-Encoding: UTF-8 
Content-Length: 138 
Last-Modified:Wed, 08 Jan 2003 23:11:55 GMT 
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux) 
ETag: "3f80f-1b6-3e1cb03b" 
Accept-Ranges:bytes 
Connection: close HTML CONTENT`

## HTTPS
Encrypted HTTP

## Criptography

### Asymetric or public key encryption
Asymmetric encryption, also known as public-key encryption, uses two keys, a public key for encryption and a corresponding private key for decryption. The public key and private key are mathematically related so that when the public key is used for encryption, the corresponding private key must be used for decryption. Two usages.
						
Public key encryption, in which a message is encrypted with a recipient's public key. The message cannot be decrypted by anyone who does not possess the matching private key, who is thus presumed to be the owner of that key and the person associated with the public keyx.

Digital signatures, in which a message is signed with the sender's private key and can be verified by anyone who has access to the sender's public key. This verification proves that the sender had access to the private key, and therefore is likely to be the person associated with the public key. This also ensures that the message has not been tampered with, as a signature is mathematically bound to the message it originally was made with, and verification will fail for practically any other message, no matter how similar to the original message.

### Symetric encryption
Symmetric encryption uses the same secret key to perform both the encryption and decryption processes.This requirement that both parties have access to the secret key is one of the main drawbacks of symmetric key encryption, in comparison to public-key encryption (also known as asymmetric key encryption).

### Symetric encryption vs asymetric encryption</li>
- Choosing between symmetric and asymmetric encryption depends on the use case. Symmetric encryption is used to share information between a set of people that all shall have access to it. Furthermore symmetric encryption is nice because it is easier to understand (less likely to mess it up) and the algorithms tend to be faster. Asymmetric encryption is used when a large number of subsets of people shall be able to share information. Furthermore asymmetric cryptography can be used in reverse to sign documents. This is especially interesting because it allows people to certify that a public key belongs to a certain person.
- The disadvantage of symmetric encryption Symmetric encryption always use the same key for encryption and decryption - that is the very definition of it. That has one major downside. If the person doing the encryption and the decryption are not the same, they have to somehow securely share the key. If A generates a random key and encrypts a message for B with it, how does he get the key to B? To do this securely, he has to transmit the key out of bound, or encrypt it with B's public key using asymmetric encryption. Obviously asymmetric encryption does not suffer from this disadvantage, since B can freely share his public key with anybody without loosing any confidentiality.
- The disadvantage of asymmetric encryption One word: Performance. It is slower than symmetric encryption. Therefore it is in general just used to encrypt a symmetric key that is used to encrypt the rest of the message.