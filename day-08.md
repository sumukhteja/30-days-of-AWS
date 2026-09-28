# Day 8: Elastic Load Balancing

Three load balancers worth knowing.

- **ALB** (layer 7): HTTP/HTTPS, routing by path, host, headers, query string. Targets can be instances, IPs, or Lambda. Great for microservices and containers.
- **NLB** (layer 4): TCP/UDP/TLS, very high performance, **static IP per AZ** (can use Elastic IPs). If the question says static IP or extreme throughput, it's NLB.
- **GWLB**: for putting third party firewalls or appliances inline. Uses GENEVE on port 6081.

Other stuff:
- Health checks decide which targets get traffic.
- **Sticky sessions** keep a user on the same target using a cookie.
- **Cross-zone load balancing**: on by default for ALB, off by default for NLB.
- SSL/TLS termination at the LB using certs from ACM. SNI lets one listener serve multiple certs.
- **Connection draining** (deregistration delay) lets in-flight requests finish before a target is removed.

The client IP on an ALB comes through the `X-Forwarded-For` header, since the backend sees the ALB's IP.
