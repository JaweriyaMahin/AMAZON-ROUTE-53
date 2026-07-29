# AMAZON ROUTE 53 DOMAIN CONFIGURATION WITH EC2

## OVERVIEW
THIS PROJECT SHOWS HOW TO CONFIGURE A CUSTOM DOMAIN PURCHASED 
FROM GODADDY USING AMAZON ROUTE 53 AND HOST A WEBSITE ON AN 
AMAZON EC2 INSTANCE WITH APACHE WEB SERVER

## SERVICES USED 
- AMAZON EC2
- AMAZON ROUTE 53
- ELASTIC IP
- GoDaddy DOMAIN REGISTRAR ( YOU CAN CHOOSE AS PER YOUR REQUIREMENT )
- APACHE HTTP SERVER

## INSTALL APACHE web server

### 1 USER DATA SCRIPT 
```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

echo "<h1>Welcome to AWS Cloud</h1><h2>Domain
Successfully Configured with Route 53</h2>" > /var/
www/html/index.html
...
.............................................................


## Output
- Website accessible using the Elastic IP.
- Website successfully accessible using the custom domain through Amazon Route 53.

## Learning Outcomes
- Domain and DNS Management
- Route 53 Hosted Zone Configuration
- GoDaddy Nameserver Configuration
- Elastic IP Association
- Apache Web Server Deployment
- DNS Verification using `nslookup` and `ping`


## created by
jaweriya mahin


  
