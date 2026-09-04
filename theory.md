# AWS Route 53

## 1. Definition

**Amazon Route 53** is a highly available and scalable **DNS (Domain Name System) web service** provided by AWS.

It is mainly used to translate **domain names into IP addresses or AWS resources** so that users can access applications using a human-readable domain name instead of an IP address.

**Example:**

`www.example.com` → `Application Server`

Route 53 can also be used for **domain registration, DNS routing, health checking, and traffic management**.

---

## 2. Why do we need Route 53?

Without DNS, users would need to remember IP addresses to access applications.

Route 53 provides:

* Domain name resolution
* DNS management
* Domain registration
* Traffic routing
* Health checking
* Failover
* Load balancing
* Routing users to applications based on different conditions

It is commonly used with services such as **EC2, Elastic Load Balancing, S3, CloudFront, and API Gateway**.

---

## 3. How does Route 53 work?

When a user enters a domain name such as:

`www.example.com`

the DNS resolution process determines where the request should be sent.

A simplified flow is:

**User → DNS Resolver → Route 53 → DNS Record → AWS Resource/Application**

For example:

`www.example.com`
↓
Route 53
↓
Application Load Balancer
↓
EC2 Instances

Route 53 returns the appropriate DNS response based on the configured DNS records and routing policy.

---

## 4. Main Components

### Hosted Zone

A **Hosted Zone** is a container for DNS records for a domain.

There are two types:

### Public Hosted Zone

Used to route traffic for domains that are accessible through the public internet.

**Example:**

`example.com`

### Private Hosted Zone

Used for DNS resolution inside one or more associated **VPCs**.

It is useful for internal applications and services that should not be publicly accessible.

---

## 5. DNS Records

DNS records tell Route 53 where and how to route traffic.

Common record types include:

### A Record

Maps a domain name to an **IPv4 address**.

**Example:**

`example.com → 192.0.2.10`

### AAAA Record

Maps a domain name to an **IPv6 address**.

### CNAME Record

Maps one domain name to another domain name.

**Example:**

`www.example.com → example.com`


### TXT Record

Stores text information associated with a domain.

It is commonly used for domain verification and email-related configurations.

### NS Record

Specifies the authoritative name servers for a domain.

### Alias Record

An AWS-specific Route 53 feature that can point a domain to supported AWS resources, such as an Application Load Balancer, CloudFront distribution, or S3 website endpoint.

---

## 6. Routing Policies

Route 53 supports different routing policies that determine how DNS queries are answered.

### Simple Routing

Used when you have a single resource for a domain.

### Weighted Routing

Distributes traffic between multiple resources based on assigned weights.

Useful for:

* Testing
* Blue/green deployments
* Gradual traffic migration

### IP-Based Routing

Routes traffic based on the source IP address of the DNS query.

---

## 7. Health Checks

Route 53 health checks monitor the health and availability of resources.

Route 53 can check whether an endpoint is responding correctly.

Health checks can be used with routing policies such as **failover routing**.

**Example:**

Primary server → Unhealthy
↓
Route 53 detects failure
↓
Traffic is directed to the secondary resource.

---

## 8. Domain Registration

Route 53 can also be used as a **domain registration service**.

You can register and manage domain names through Route 53 and configure their DNS records.

**Example:**

`example.com`

After registering the domain, DNS records can be configured through Route 53.

---

## 9. TTL

**TTL (Time To Live)** specifies how long DNS resolvers should cache a DNS response.

For example:

**TTL = 300 seconds**

The DNS response can be cached for approximately 5 minutes before another DNS lookup is normally required.

A lower TTL can help changes propagate faster, while a higher TTL can reduce DNS query frequency.

---

## 10. Route 53 with AWS Services

Route 53 can work with many AWS services.

### Route 53 + EC2

A domain name can resolve to an EC2-based application.

### Route 53 + ELB

A domain can route users to an Application Load Balancer or Network Load Balancer.

**User → Route 53 → Load Balancer → EC2**

### Route 53 + CloudFront

Route 53 can direct users to a CloudFront distribution.

**User → Route 53 → CloudFront → Origin**

### Route 53 + S3

Route 53 can be used with supported S3 website hosting configurations to provide a custom domain.

---

## 11. Public vs Private Hosted Zone

| Public Hosted Zone              | Private Hosted Zone                    |
| ------------------------------- | -------------------------------------- |
| Used for public DNS             | Used for internal DNS                  |
| Accessible through the internet | Used within associated VPCs            |
| Example: public website         | Example: internal application          |
| Resolves public domain names    | Resolves private/internal domain names |



## 12. Important Features

Key Route 53 features include:

* DNS service
* Domain registration
* Public hosted zones
* Private hosted zones
* DNS records
* Health checks
* Traffic routing
* Failover
* Latency-based routing
* Weighted routing
* Geolocation routing
* Geoproximity routing
* Multi-value answer routing
* IP-based routing
* Integration with AWS services

