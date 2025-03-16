# Installing Docker on AWS EC2

## Prerequisites
- AWS account with permissions to create an EC2 instance.
- An EC2 instance (Amazon Linux 2, Ubuntu, or any other supported OS).
- SSH access to the instance.

## Step 1: Connect to the EC2 Instance
First, connect to your EC2 instance using SSH:
```sh
ssh -i your-key.pem ec2-user@your-instance-ip
```
Replace `your-key.pem` with your SSH key and `your-instance-ip` with the public IP of your EC2 instance.

## Step 2: Update the System Packages
Before installing Docker, update the system packages:
```sh
sudo yum update -y  # For Amazon Linux
sudo apt update -y  # For Ubuntu
```

## Step 3: Install Docker
### Amazon Linux 2
```sh
sudo yum install docker -y
```
### Ubuntu
```sh
sudo apt install docker.io -y
```

## Step 4: Start and Enable Docker Service
After installation, start and enable Docker so it runs at boot:
```sh
sudo systemctl start docker
sudo systemctl enable docker
```

## Step 5: Verify Docker Installation
Check if Docker is running properly:
```sh
docker --version
sudo docker run hello-world
```
If the `hello-world` container runs successfully, Docker is installed and working.

## Step 6: Add User to the Docker Group (Optional)
By default, Docker commands require `sudo`. To allow your user to run Docker without `sudo`, add it to the Docker group:
```sh
sudo usermod -aG docker $USER
newgrp docker
```

## Step 7: Enable Docker on Reboot
```sh
sudo systemctl enable docker
```

## Step 8: Configure Firewall (If Required)
If your application needs to be accessible over the internet, open necessary ports:
```sh
sudo firewall-cmd --zone=public --add-port=80/tcp --permanent
sudo firewall-cmd --reload
```
For AWS Security Groups, allow inbound traffic on required ports via the AWS console.

## Step 9: Test Docker by Running a Container
Run a simple Nginx container to test:
```sh
docker run -d -p 80:80 --name nginx-test nginx
```
Access the instance's public IP in a browser to verify Nginx is running.

## Conclusion
You have successfully installed Docker on AWS EC2 and verified its functionality. Now you can deploy containerized applications efficiently.
