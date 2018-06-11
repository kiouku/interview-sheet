## REST

### Definition
REST is a software design pattern typically used for web applications. In layman's terms this means that it is a commonly used idea used in many different projects. It stands for REpresentational State Transfer. The basic idea of REST is treating objects on the server-side (as in rows in a database table) as resources than can be created or destroyed.

The most basic way of thinking about REST is as a way of formatting the URLs of your web applications. For example, if your resource was called "posts", then:

/posts Would be how a user would access ALL the posts, for displaying.

/posts/:id Would be how a user would access and view an individual post, retrieved based on their unique id.

/posts/new Would be how you would display a form for creating a new post.
 
### Fundamental REST principles 

- Client-Server Communication: Client-server architectures have a very distinct separation of concerns. All applications built in the RESTful style must also be client-server in principle.

- Stateless: Each client request to the server requires that its state be fully represented. The server must be able to completely understand the client request without using any server context or server session state. It follows that all state must be kept on the client. We will discuss stateless representation in more detail later.

- Cacheable: Cache constraints may be used, thus enabling response data to to be marked as cacheable or not-cachable. Any data marked as cacheable may be reused as the response to the same subsequent request.

- Uniform Interface: All components must interact through a single uniform interface. Because all component interaction occurs via this interface, interaction with different services is very simple. The interface is the same! This also means that implementation changes can be made in isolation. Such changes, will not affect fundamental component interaction because the uniform interface is always unchanged. One disadvantage is that you are stuck with the interface. If an optimization could be provided to a specific service by changing the interface, you are out of luck as REST prohibits this. On the bright side, however, REST is optimized for the web, hence incredible popularity of REST over HTTP

## RESTful 
It is typically used to refer to web services implementing such an architecture.

