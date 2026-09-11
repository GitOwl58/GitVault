#domain/networking

### **CDN (Content Delivery Network)**

A geographically distributed network of proxy servers ("edge servers") that cache and deliver content from locations physically closer to end users, reducing latency and origin server load.

- Origin server holds the original content; CDN edge nodes cache copies
- User requests are routed to the nearest/best-performing edge server (often via DNS or Anycast)
- Reduces latency, bandwidth costs, and improves availability/resilience (DDoS mitigation, load distribution)
- Common use: static assets (images, CSS, JS, video streaming), but modern CDNs also handle dynamic content and edge computing

### Related
[[DNS]]  [[TCP]]  [[HTTP]]  [[TTL]]

### Sources
[[23. Putting it all together]]