#domain/networking

# URL (Uniform Resource Locator)

Instruction on how to access a resource on the internet, made up of several parts:

- **Scheme**: protocol to use — [[HTTP]]/HTTPS/[[FTP]]
- **User**: optional username/password for services requiring authentication
- **Host**: domain name or [[IP address]] of the server
- **Port**: port to connect to (default 80 for HTTP, 443 for HTTPS) — see [[Ports]]
- **Path**: file or location of the resource being requested
- **Query string**: extra parameters passed to the path (e.g. `/blog?id=1`)
- **Fragment**: reference to a specific location within the requested page

Resolving the host to an [[IP address]] is handled via [[DNS]].

### Related:
[[HTTP]] · [[DNS]] · [[TLD]] · [[Ports]] [[IP address]] [[Networking]] [[Web server]] 

### Source:
[[2. Client-server Basics]] 
[[21. HTTP in detail]]
