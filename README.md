# Prerequisites:
1. An AWS account.
2. Basic knowledge of the Linux command line (if using a Linux-based instance).
3. A web application ready to be deployed.

## Launch an EC2 Instance
1. Go to the EC2 service from the console.
2. Click on Launch Instance.
3. Choose an Amazon Machine Image (AMI). For a dynamic website, you typically select a Linux distribution (e.g., Amazon Linux 2, Ubuntu) or a Windows Server if your application requires it.
4. Choose an instance type. For small-scale projects, a t2.micro or t3.micro (which are eligible for the free tier) should be sufficient.
5. Add storage. The default 8 GB of EBS (Elastic Block Store) is often enough, but you can adjust it based on your needs.
6. Configure security groups. Add rules to allow HTTP (port 80) and HTTPS (port 443) traffic. Also, allow SSH (port 22) or RDP (port 3389) for accessing the instance.
7. Review your settings, then click Launch.
8. Choose or create a new key pair for SSH access, download the .pem file,or .ppk file and store it securely.
Launch the instance.

## Connect to Your EC2 Instance
### Using SSH (Linux/Mac) or PuTTY (Windows):
1. Open a terminal (Linux/Mac) or PuTTY (Windows).
2. Connect to your instance using the following command (replace `your-key.pem` or `your-key.ppk` with your key file and `ec2-user@your-public-ip` with your instance’s public IP):

```bash
ssh -i "your-key.pem" ec2-user@your-public-ip

```
3. For Windows users, use PuTTY with the corresponding `.ppk` key file.
4. Once connected, update your instance’s package lists:
   ```bash
     sudo apt update -y  

   ```
## Install a Web Server
1. Install Apache or Nginx

For Apache:
```bash
   sudo apt install apache2 -y 
```

For Nginx: 
```bash
   sudo apt install nginx -y
```
2. Start and Enable the Web Server:

For Apache:
```bash
   sudo systemctl start httpd
   sudo systemctl enable httpd
```

for Nginx:
```bash
   sudo systemctl start nginx
   sudo systemctl enable nginx
```
3. Access your instance’s public IP address in a browser. You should see the default Apache or Nginx welcome page.
   
## Install and Configure a Database (Optional)
1. Install MySQL:
```bash
   sudo apt install mysql-server -y
```
2.  Start and Enable the Database Service
```bash
   sudo systemctl start mysqld
   sudo systemctl enable mysqld
```
3. Secure the Database Installation
```bash
   sudo mysql_secure_installation
```
