# EC2 Security Groups - The Firewall

## What ARE Security Groups?
- They are **virtual** firewalls in AWS that control what traffic can reach my EC2 instances.

### Simple Definition
- Your EC2 instance is my house.
- the Security Group = the security guard at my gate who checks IDs and decides who gets in and who doesn't.
  


## How Security Groups Work
### Inbound Rules = Who Can ENTER
- The security guard checks who can enter.
- Inbound rules checks what traffic can reach my ec2 instance from the internet / other sources
- this is set o default = **deny**

#### Example Inbound Rules: 
**- Port 22 (SSH) --> IP**
    Type: SSH (port 22)
    Source: My IP only (xx.xxx.xx.)
    Action: Allow
- Only I can SSH into this server from my IP

**- Type: HTTP (port 80)** (unsecured)
Source: Anywhere (0.0.0.0/0)
Action: Allow
ANYONE on internet can access my website

Type: HTTPS (port 443) secured 
Source: Anywhere (0.0.0.0/0)
Action: Allow
→ ANYONE can access your secure website

### Outbound Rules = What Can LEAVE
- This is set to default = allow 

### Key Characteristics
1. Stateful
   - If I allow inbound traffic, i dont need to allow outbound traffic as they will be able to go out once they are allowed
     
2. Deny by default:
   - Access to my ec2 instance from inbound traffic is automatically set to deny
     
3. Only ALLOW rules:
   - there are no DENY rules as returned traffic is auto allowed was inbound traffic is allowed
     
4. Multiple security groups
   - One instance can have multiple security groups 

## Common Ports to Know

| Port | Protocol | Use Case |
|------|----------|----------|
| 22 | | SSH/SFTP | Accessing my instance/server from my computer ; SSH file to 
| 3389 | RDP      | Remote desktop protocol to windows servers
| 80 | | HTTP     | traffic from any source to my website 
| 443  | https    | traffic from anywhere to my secured website 
| 3306 | MySQL    | Database
| 5432 | PostgreSQL|Database 
| 21   | FTP       | Upload file 

## Security Groups vs. Network ACLs

### Security Groups
- Evaluate all rules before deciding 
- Stateful i.e means return traffic is auto allowed 
- Operate at the instance level 
- Only ALLOW rules


## Real-World Security Group Example

### Scenario: Web Application with Database

#### Web Server Security Group

Inbound:
- HTTP (80) from anywhere → public access to website
- HTTPS (443) from anywhere → secure public access
- SSH (22) from YOUR IP only → you can manage server

Outbound:
- All traffic allowed --> server can download updates, connect to database


#### Database Security Group
Inbound:
- MySQL (3306) from Web Server Security Group ONLY --> only web servers can access database
- NO SSH, NO HTTP --> database not directly accessible from internet

Outbound:
-  All traffic allowed → database can send responses back 


### Security Logic
- Hackers cannot brutforce hack the database for cryptomining
- Public can access my website
- Web servers can access my database
- I can manage my webservers 

## FinOps Perspective on Security Groups - in my FinOps file 

