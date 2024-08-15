# Prerequisites:
1. An AWS account.
2. Basic knowledge of the Linux command line (if using a Linux-based instance).
3. A web application ready to be deployed.

## Step 1: Launch an EC2 Instance
1. Go to the EC2 service from the console.
2. Click on Launch Instance.
3. Choose an Amazon Machine Image (AMI). For a dynamic website, you typically select a Linux distribution (e.g., Amazon Linux 2, Ubuntu) or a Windows Server if your application requires it.
4. Choose an instance type. For small-scale projects, a t2.micro or t3.micro (which are eligible for the free tier) should be sufficient.
5. Add storage. The default 8 GB of EBS (Elastic Block Store) is often enough, but you can adjust it based on your needs.
6. Configure security groups. Add rules to allow HTTP (port 80) and HTTPS (port 443) traffic. Also, allow SSH (port 22) or RDP (port 3389) for accessing the instance.
7. Review your settings, then click Launch.
8. Choose or create a new key pair for SSH access, download the .pem file,or .ppk file and store it securely.
Launch the instance.

## Step 2: Connect to Your EC2 Instance
### Using SSH (Linux/Mac) or PuTTY (Windows):
1. Open a terminal (Linux/Mac) or PuTTY (Windows).
2. Connect to your instance using the following command (replace `your-key.pem` or `your-key.ppk` with your key file and `ec2-user@your-public-ip` with your instance’s public IP):

``
ssh -i "your-key.pem" ec2-user@your-public-ip
``

