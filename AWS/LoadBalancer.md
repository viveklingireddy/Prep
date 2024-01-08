### Load Balancer  

Load Balancers are used to distribute users requests to  the servers equally, They balance the traffic to many servers to make them high available, scalable, security and have high fault tolerance.  
- When a Incoming request to xyz.com, it distributes to the server that is geographically closer to reduce latency, and also requests area equally distributed with load balancing algorithms.
- with Load balancers it is usefull to maintain down of servers etc. When a instance is not accesible/ having issues it is transfer to other available istances. It performs health checks
- Security: Load Balancers offers additional security for incoming traffic. It defence the Denial of Service attacks, they monitor the traffic and block malicious content.   
- Availability: You can easily have maintanence or upgrades without down time 
- Scalability: It can access thousands of requests by distributing among the servers. From insights of traffic, you can track. So you have add/ delete of servers.
 

- Usually Companies have larger number of servers, they run application on multiple servers to make globally  available across the regions to users. This arrangement of many servers is  called serverfarm.  
So When I want to access the Walmart.com, the request from DNS goes to the Load Balancer. It sends to the server that is closer to the region and available. 
-  
![LoadBalancer](Images/LoadBalancer.png)
  
![Load Balancing](https://www.cloudflare.com/learning/performance/what-is-load-balancing/)

### **ApplicationLoadBalancer** 
### **Network LoadBalancer**
### **GlobalServerLoadBalancer**
### **DNS LoadBalancer**

**Elastic Load Balancing (ELB)** is a fully managed load balancing service that automatically distributes incoming application traffic to multiple targets and virtual appliances across AWS and on-premises resources. You can use it to scale modern applications without complex configurations or API gateways. You can use ELB to set up four different types of software load balancers.

- An Application Load Balancer routes traffic for HTTP-based requests.

- A Network Load Balancer routes traffic based on IP addresses. It is ideal for balancing TCP and User Datagram Protocol (UDP)-based requests.

- A Gateway Load Balancer routes traffic to third-party virtual appliances. It is ideal for incorporating a third-party appliance, such as a network firewall, into your network traffic in a scalable and easy-to-manage way.

- A Classic Load Balancer routes traffic to applications in the Amazon EC2-Classic network—a single, flat network that you share with other customers.
- Setting up the ELB on aws 
- Create VPC, add 2 public subnets on different regions, create internet gateway and add route table to it  
- Now create 2 Ec2 instance on both the subnets with user data



# Update and install Apache

```bash
#!/bin/bash
sudo yum update -y
sudo yum install httpd -y
sudo service httpd start
sudo chkconfig httpd on


# Get the instance's hostname and public IP address

```bash
hostname=$(curl -s http://169.254.169.254/latest/meta-data/hostname)
public_ip=$(curl -s http://169.254.169.254/latest/meta-data/public-ipv4)


# Create an HTML file displaying hostname and IP address
```bash
echo "<h1>Hostname: $hostname</h1>" > /var/www/html/index.html
echo "<p>Public IP Address: $public_ip</p>" >> /var/www/html/index.html



### Target Group 
- we place all the components inside the vpc into target group so load balancer can transfer to any of them depending on availability. 


USERDATA 

```bash
sudo apt update -y
sudo apt install apache2 -y
echo "<h1>Server Details</h1><p><strong>Hostname:</strong> $(hostname)</p><p><strong>IP Address:</strong> $(hostname -I)</p>" | sudo tee /var/www/html/index.html
sudo systemctl restart apache2


```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html


